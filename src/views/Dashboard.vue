<template>
    <div>
        <div>
            <nav class="navbar navbar-expand-lg navbar-light bg-light">
                <div class="container-fluid">
                        <a class="navbar-brand" href="/">LOGDATA</a>
                        
                        <div class="collapse navbar-collapse" id="navbarSupportedContent">
                        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                            <li class="nav-item">
                            </li>
                        </ul>
                        <form class="d-flex">
                            <router-link class="btn btn-outline-primary my-2 my-sm-0" to="/login">logout</router-link>
                        </form>
                        </div>
                </div>
            </nav>
        </div>
        <div>
            <h1>Welcome {{this.$route.params.curruser}}</h1>
        </div>
        <br>
        <div class="row">
            <div class="col-md-3"></div>
            <div class="col-md-9">
                <table class="table table-bordered" v-if="username=='Admin'">
                    <tr>
                        <th>Name</th>
                        <th>Username</th>
                    </tr>
                    <tr v-for="user in users" v-bind:key="user">
                        <td>{{user.name}}</td>
                        <td>{{user.username}}</td>
                    </tr>
                </table>
            </div>
            <div class="col-md-3"></div>
            
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
<style scoped>
table{
    justify-content: center;
    border: black solid;
    background-color: aquamarine;
    width: 50%;
}
.col-md-9{
    padding-left: 80px;
}
</style>
 