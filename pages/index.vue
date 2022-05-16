<template>
  <div class="smth">
    <Header />
    <Login />
  </div>
</template>

<script>
import Header from "../components/Header/Header.vue"
import Login from "../components/LoginForm/Login.vue"
export default {
  components: {
    Header, Login
  },
  data(){
    return {
      login: "LOGIN"
    }
  }
}
</script>

<style>
  *{
      margin: 0;
      padding: 0;
  }
</style>