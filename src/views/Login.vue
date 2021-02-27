<template>
    <div>
        <Navbar />
        <div class="container">
        <h1>Login to Dashboard</h1>
        <br>
        <br>
        <div class="row">
        <div class="col-md-3"></div>
        <div class="col-md-6">
            <div>
            <div class="mb-3">
                <input
                type="text"
                class="form-control"
                id="username"
                placeholder="Enter Username"
                />
            </div>
            <div class="mb-3">
                <input
                type="password"
                class="form-control"
                id="password"
                placeholder="Password"
                />
            </div>
            <button class="btn btn-primary" @click="login()" >Login</button>
            </div>
        </div>
        <div class="col-md-3"></div>
        </div>
        </div>
    </div>
</template>

<script>
import Navbar from "../components/Navbar"
export default {
    components: {
    Navbar
    },
    methods:{
        login: function(){
            
            let localStorage = window.localStorage;
            let users_str=localStorage.getItem("users");
            let username = document.getElementById("username").value;
            
            let password = document.getElementById("password").value;
            let users = [];
            if(users_str!=null){
                users = JSON.parse(users_str);
            }

            if(document.getElementById("username").value=="admin" && document.getElementById("password").value=="admin")
            {
                 this.$router.push({ name: 'Dashboard',params:{users,curruser:"Admin"} })
            }
            
            else{
                let flag = 0;
                let curruser = null;
                for(let i in users){
                
                    if(users[i].username==username && users[i].password==password){
                        flag=1;
                        curruser=users[i].username;
                    }
                }

                if(flag){
                    console.log("login Successful");
                    this.$router.push({ name: 'Dashboard',params:{users,curruser} })
                    
                }else{
                    console.log("Incorrect Username/password")
                }
                
            }
            
            
        }
    }
};
</script>

<style scoped>
</style>