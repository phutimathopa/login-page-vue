<template>
    <div id="app">
         <register></register>
          <login @myEvent="setAuthenticated" v-if ="!authenticated"></login>
          <secure @myEvent="setAuthenticated" v-else =""></secure>
    </div>
</template>

<script>
import login from './components/Login.vue'
import secure from  './views/secure.vue'
import register from './components/Register.vue'

    export default {
        name: 'App',
        data() {
            return {
                authenticated: false,
                mockAccount: {
                    username: "1",
                    password: "1"
                }
            }
        },
        mounted() {
           
        },
        components: {
            login,
            register,
            secure
            
        },
        methods: {
            setAuthenticated(status) {
                this.authenticated = status;
            },
            logout() {
                this.authenticated = false;
            }
        }
    }
</script>

<style>
    body {
        background-color: #F0F0F0;
    }
    h1 {
        padding: 0;
        margin-top: 0;
    }
    #app {
        width: 1024px;
        margin: auto;
    }
</style>
