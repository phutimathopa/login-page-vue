<template>
    <div>
        <h4>Register</h4>
        <form>
            <label for="username">Name</label>
            <div>
                <input id="username" type="text" v-model="username" required autofocus>
            </div>

            <label for="password">Password</label>
            <div>
                <input id="password" type="password" v-model="password" required>
            </div>

            <div>
                <button type="submit" @click="handleSubmit">
                    Register
                </button>
            </div>
        </form>
    </div>
</template>

<script>
    export default {
        data(){
            return {
                username : "",
                password : ""
            }
        },
        methods : {
        
            handleSubmit(e){
                e.preventDefault()
                if(this.input.username != "" && this.input.password != "") {
                   this.$emit('myEvent',true) 
                    .then(response => {

                    })
                    .catch(function (error) {
                        console.error(error.response);
                    });
                }
            }
        }
    }
</script>