<template>
  <div>
      <h1>UserManager</h1>
      <button v-on:click="createUser('alain', 'alain@gmail.com')">add user</button>
      <button v-on:click="getUser()">get users</button>
      <ul>
          <li  v-for="user in users.data"> {{user.username}} - {{user.email}} <a class="delete" href="/" v-on:click="deleteUser($event)">delete</a></li>
      </ul>
  </div>
</template>
<script>
    module.exports = {
        data: function(){
            return{
                users: [],
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
                var vm = this;
                this.axios.get('http://localhost:4000/api/users').then(function (response) {

                         vm.$data.users = response.data

                        console.log(vm.$data.users);
                    })
                    .catch(function (error) {
                        console.log(error);
                    });
            },
            deleteUser: function(event){
                event.preventDefault()
                let url = event.target.attributes.href;
                console.log(this);

            }
        }
    }

</script>
<style scoped>
 h1{
     color: red;
 }
</style>