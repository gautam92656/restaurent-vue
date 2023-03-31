<template>
  <div class="sign">
    <h1>Sign Up</h1>

    <div class="form">
      <div class="uname">
        <input type="text" name="username" v-model="user" class="input" placeholder="Enter Username"/>
      </div>
      <div class="email">
        <input type="email" name="mail" v-model="email" class="input" placeholder="Enter Email" />
      </div>
      <div class="passw">
        <input type="password" name="password" v-model="password" class="input" placeholder="Enter password" />
      </div>
      <button v-on:click="Sign()" class="btn">Sign Up</button>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "SignUp",
  data() {
    return {
      user: "",
      password: "",
      email: ""
    };
  },
  methods: {
    async Sign() {
        let result= await axios.post ("http://localhost:3000/user" , {
            username : this.user,
            email : this.email,
            password : this.password

        })
      console.log("data" , result.data) 
      if (result.status==201) {
        alert("you have successfully registered !!!!!!!!!!!!!!")
      }
      localStorage.setItem ("signup data" , JSON.stringify (result.data))
    },
  },
};
</script>

<style scoped>
h1{
    margin: 10px;
    padding-bottom: 20px;
}
.input{
    margin: 10px;
    padding: 10px 15px;
    font-size: 18px;
    border-radius: 5px;
    border: 1px solid black;
}
.btn{
    margin-top: 30px;
    border: 1px solid black;
    border-radius: 20px;
    padding: 10px 20px;
    font-size: 20px;
    background-color: black;
    color: white;
}
</style>
