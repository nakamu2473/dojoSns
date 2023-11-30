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
                    ユーザー情報編集
                </v-card-text>
                <v-card-text>
                    <v-text-field
                    v-model="user"
                    label="user"
                    placeholder="名前"
                    ></v-text-field>
                    <v-text-field
                    v-model="id"
                    label="id"
                    placeholder="ユーザーID"
                    ></v-text-field>
                    <v-text-field
                    v-model="pass"
                    label="pass"
                    placeholder="パスワード"
                    ></v-text-field>
                </v-card-text>
                <v-btn
                    color="primary"
                    variant="text"
                    @click="update()"
                >
                更新にゃ
                </v-btn>
                <v-card-text
                    v-for="item in notes"
                    v-bind:key="item">
                    {{ item }}
                </v-card-text>
            </v-card>
        </v-col>
    </v-row>
    
    </template>
    <script>
    export default{
        data(){
            return {
                user:"",
                id:"",
                pass:""
            }
        },
        methods:{
            update() {
                localStorage.setItem("user", this.user)
                localStorage.setItem("id", this.id)
                localStorage.setItem("pass", this.pass)
                this.$router.push("../list") 
            },
        },
        mounted() {
            if(!localStorage.getItem("user")) {
                this.$router.push("/") 
            }
        }
    }
    </script>