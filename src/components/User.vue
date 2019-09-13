<template>
  <div>
      <h1>UserManager</h1>
      <button v-on:click="createUser('fred', 'fred@gmail.com')">add user</button>
  </div>
</template>
<script>
    module.exports = {
        data:function(){
            return{
                data:{}
            }
        },
        methods: {

            createUser: function(nom, email){
                this.axios.post('http://localhost:4000/api/users', {
                    user:{
                    username: nom,
                    email: email}
                })
                    .then(function (response) {
                        console.log(response);
                    })
                    .catch(function (error) {
                        console.log(error);
                    });
            },
            getUser: function(){

            },
            deleteUser: function(){


            }
        }
    }

</script>
<style scoped>
 h1{
     color: red;
 }
</style>