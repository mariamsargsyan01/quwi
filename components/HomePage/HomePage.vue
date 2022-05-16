<template>
    <div class="homePage">
        <Header :text="logoutTxt" :logout="logout"/>
        <Modal :text="newName" :isOpen="!open" :isClose="!close" :submitNewName="submitNewName" :cancel="cancel" :typeInput="typeInput" />
        <div class="wrapper">
            <div v-for="project in projectsList" :key="project.id" class="project" :class="{notVisible: notVisible}">
                <Project :name="project.name" :id="project.id" :isActive="project.is_active ? `Active` : `Inactive`" :logo="project.logo_url" :changeName="changeNameFunc"/>
            </div>
        </div>
    </div>
</template>

<script>
import Header from "../Header/Header.vue"
import Project from "./Project/Project.vue"
import Modal from "../HomePage/Modal/Modal.vue"
import axios from "axios"
export default {
    components: {
        Project, Header, Modal
    },
    data(){
        return {
            projectsList: [],
            open: true,
            close: false,
            notVisible: false,
            projectName: "",
            projectId: "",
            newName: "",
            logoutTxt: "LOGOUT"
        }
    },
    methods: {
        typeInput(e){
            this.newName = e.target.value
        },
        changeNameFunc(name, id){
            this.open = false
            this.close = true
            this.notVisible = true
            this.projectId = id
            this.projectName = name
        },
        submitNewName(){
            if (this.newName !== ""){
                this.open = true
                this.close = false
                this.notVisible = false
                const form = new FormData();
                form.append("name", this.newName);

                const options = {
                method: 'POST',
                url: 'https://api.quwi.com/v2/projects-manage/update',
                params: {id: this.projectId},
                headers: {
                    Authorization: `Bearer ${localStorage.getItem("token")}`,
                    'content-type': 'multipart/form-data; boundary=---011000010111000001101001'
                },
                data: form
                };

                axios.request(options).then((response) => {
                const item = this.projectsList.find(
                (item) => item.id === response.data.project.id);
                item.name = response.data.project.name;
                this.newName = ""
                }).catch(function (error) {
                console.error(error);
                });
            }
        },
        cancel(){
            this.open = true
            this.close = false
            this.notVisible = false
            this.newName = ""
        },
        logout(){
            localStorage.removeItem("token")
            this.$router.push({ path: "/" });
        }
    },
    mounted(){
        if (!localStorage.getItem("token")) {
            this.$router.push({ path: "/" });
        }

        const form = new FormData();
        const options = {
        method: 'GET',
        url: 'https://api.quwi.com/v2/projects-manage',
        headers: {
            'Content-Type': 'multipart/form-data; boundary=---011000010111000001101001',
            Authorization: `Bearer ${localStorage.getItem("token")}`
        },
        data: form
        };

        axios.request(options).then((response) => {
        this.projectsList = response.data.projects;
        }).catch(function (error) {
        console.error(error);
        });
    }
}
</script>

<style src="./HomePageStyle.vue"></style>


