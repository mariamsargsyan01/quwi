<template>
    <div class="section">
        <div class="modal">
            <div class="title">
                <div class="iconWrapper">
                    <img src="../pics/quwi-logo.png" width="40px" height="40px" />
                </div>
                <p>QUWI</p>
            </div>
            <div class="inputSection">
                <div class="inputField">
                    <p class="inputTitle" :class="{ emailEmpty: isEmailEmpty }">Email</p>
                    <input v-model="email" @input="checkEmail" placeholder="email" type="email"/>
                </div>
                <div class="inputField">
                    <p class="inputTitle" :class="{ passwordEmpty: isPasswordEmpty }">Password</p>
                    <input v-model="password" @input="checkPassword" placeholder="password" type="password"/>
                </div>
                <button @click="login()">Login</button>
                <p class="forgotPass">Forgot password?</p>
            </div>
        </div>
    </div>
</template>

<script>
import axios from "axios";

export default {
    data(){
        return {
            email: "",
            password: "",
            isEmailEmpty: true,
            isPasswordEmpty: true
        }
    },
    mounted() {
        if (localStorage.getItem("token")) {
            this.$router.push({ path: "/homepage" });
        }
    },
    methods: {
        checkEmail(){
            this.email ? this.isEmailEmpty = false : this.isEmailEmpty = true
        },
        checkPassword(){
            this.password ? this.isPasswordEmpty = false : this.isPasswordEmpty = true
        },
        login(){
            const options = {
            method: 'POST',
            url: 'https://api.quwi.com/v2/auth/login',
            headers: {
                cookie: '_csrf=0431cb316b10a594b7092b9e22e000e3d35c06b9899faea34df6c78ca81a9304a%253A2%253A%257Bi%253A0%253Bs%253A5%253A%2522_csrf%2522%253Bi%253A1%253Bs%253A32%253A%2522c9pZZ2KRBRIxUcB80S0oCnRlY-aQtAgo%2522%253B%257D',
                'Content-Type': 'application/json',
                'Client-Device': 'desktop',
                'Client-Timezone-Name': 'Asia/Armenia'
            },
                data: {email: this.email, password: this.password}
            };

            axios.request(options).then((response) => {
            localStorage.setItem("token", response.data.token);
            this.$router.push({ path: "/homepage" });
            }).catch(function (error) {
            console.error(error);
            });
        }
    }
}
</script>

<style src="./LoginStyle.vue"></style>
