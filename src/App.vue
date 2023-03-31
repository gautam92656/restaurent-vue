<template>
  <div class="main">
    <img alt="logo" src="./assets/restaurent-logo.webp" class="logo" />
    <SignUp />
  </div>
</template>

<script>
import SignUp from "./components/signUp.vue";

export default {
  name: "App",
  components: {
    SignUp,
  },
};
</script>

<style>
template {
  margin: 0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.logo {
  width: 200px;
}
</style>
