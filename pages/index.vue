<template>
    <v-row justify="center">
      <v-col
        cols="12"
        sm="10"
        md="8"
        lg="6"
        >
        <v-card ref="form">
          <v-card-text>
            <v-text-field
              v-model="input.username"
              label="Full Name"
              placeholder="John Doe"
            ></v-text-field>

            <v-text-field
                v-model="input.password"
                name="input-10-1"
                label="Normal with hint text"
            ></v-text-field>
            </v-card-text>
            <div>
                <input type="text" v-model="input.username">
                <input type="text" v-model="input.password">

            </div>
            <p>{{  loginArea() }}</p>
            <v-btn
            color="primary"
            variant="text"
            @click="login"
            :disable="!loginArea" 
          >
          login
          </v-btn>
      </v-card>
    </v-col>
  </v-row>
</template>
  <script>
  export default{
      data(){
          return {
              input: {
                  username: "",
                  password: ""
              },
                loginMsg: ""

          }
      },
      methods:{
        loginArea() {
            if(this.input.username != "user") return false
            if(this.input.password != "pass") return false
            localStorage.setItem("name", "user")
            return true
        },
        login() {
            this.$router.push("/list") 
        }
      }
  }
  </script>