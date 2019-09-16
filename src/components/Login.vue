<template>
    <div id="login">
   
    
        <h1>Login</h1>
        <input type="text" name="username" v-model="input.username" placeholder="Username" />
        <h2><input type="password" name="password" v-model="input.password" placeholder="Password" /></h2>

        <button type="button" v-on:click="login()">Login</button>
        
        <button type="button" v-on:click="register()">register</button>
    </div>
</template>

<script>
import RegisterVue from './Register.vue';

    export default {
        name: 'Login',
        data() {
            return {
                
                input: {
                    username: "",
                    password: ""
                }
            }
        },
        methods: {
            login() {
                if(this.input.username != "" && this.input.password != "") {
                   this.$emit(RegisterVue,false) 
            }
        }
 
    }
}
</script>

<style scoped>
    #login {
        width: 500px;
        border: 1px solid #CCCCCC;
        background-color: #FFFFFF;
        margin: auto;
        margin-top: 200px;
        padding: 20px;
    }
</style>