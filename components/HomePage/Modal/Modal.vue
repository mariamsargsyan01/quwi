<template>
    <div :class="{openModal: isOpen, closeModal: isClose}">
        <div class="newName">
            <input @input="typeInput" :value="text" placeholder="New Name"/>
            <button class="submitBtn" @click="submitNewName()">Submit New Name</button>
            <button class="cancelBtn" @click="cancel()">Cancel</button>
        </div>
    </div>
    
</template>

<script>
export default {
    props: {
        isOpen: Boolean,
        isClose: Boolean,
        text: String,
        submitNewName: Function,
        typeInput: Function,
        cancel: Function
    },
}
</script>

<style src="./ModalStyle.vue"></style>