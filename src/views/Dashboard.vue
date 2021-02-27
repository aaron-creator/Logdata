<template>
<div>
    <router-link class="btn btn-outline-primary my-2 my-sm-0" to="/login">logout</router-link> 
    <div>
        <h1>Welcome {{this.$route.params.curruser}}</h1>
    </div>
    <div  v-if="username=='Admin'">
    <div v-for="user in users" v-bind:key="user">
        <p>{{user.name}}</p>
     </div>
    </div>
</div>

  
</template>

<script>
export default {
    mounted(){
        this.init();
    },
 data: function(){
     return{
     username:this.$route.params.curruser,
       users:this.$route.params.users,
     }
     
},
methods:{
    init(){
        console.log(this.$route.params);
    },
    logout(){
        window.location="/login";
    }
}
}
</script>
 