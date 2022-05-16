<template>
    <div class="header">
        <div class="icon">
            <img src="../pics/quwi-logo.png" width="25px" height="25px" />
        </div>
        <div class="signup" @click="logout()">{{text}}</div>
    </div>
</template>

<script>
export default {
    props: {
        text: String,
        logout: Function
    },
}
</script>

<style  src="./HeaderStyle.vue"></style>
