<template>
    <div>
      index
    </div>
    <nuxt-link to="/aaa">aaa</nuxt-link>
    <nuxt-link to="/bbbb">bbbb</nuxt-link>
    <nuxt-link to="/hoge">hoge</nuxt-link>
    <nuxt-link to="/hoge/aaa">hoge-aaa</nuxt-link>
    <div>
        <input type="text" v-model="input.username">
        <input type="text" v-model="input.password">
    </div>
    <p>{{  loginArea() }}</p>
    <button :disable="!loginArea" @click="login">login</button>
  </template>
  <script>
  export default{
      data(){
          return {
              input: {
                  username: "",
                  password: ""
              }
          }
      },
      methods:{
        loginArea() {
            if(this.input.username != "user") return false
            if(this.input.password != "password") return false
            return true
        },
        login() {
            this.$router.push("/aaa") 

        }
      }
  }
  </script>