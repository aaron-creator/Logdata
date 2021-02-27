<template>
  <div class="container-fuild">
      <Navbar />
      <div class="container">
        <h1>Register in LOGDATA</h1>
        <br />
        <br />
        <div class="row">
          <div class="col-md-3"></div>
          <div class="col-md-6">
            <div>
              <div class="mb-3">
                <input
                  type="text"
                  class="form-control"
                  id="fullname"
                  aria-describedby="emailHelp"
                  placeholder="Enter Full Name"
                />
              </div>
              <div class="mb-3">
                <input
                  type="username"
                  class="form-control"
                  id="username"
                  placeholder="Enter username"
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
              <div class="mb-3">
                <input
                  type="password"
                  class="form-control"
                  id="cpassword"
                  placeholder="Confirm Password"
                />
              </div>
              <button class="btn btn-primary" @click="reg()" >Register</button>
            </div>
          </div>
          <div class="col-md-3"></div>
        </div>
      </div>
  </div>
</template>

<script>
import Navbar from "../components/Navbar.vue"
export default {
    components: {
    Navbar
    },
    methods:{
        reg: function(){
            const regName = /^[A-Z][a-z]{3,30}(\s[A-Z](\.|[a-z]{2,30})?)*$/;
            let localStorage = window.localStorage;
            let users_str=localStorage.getItem("users");
            let users = [];
            if(users_str!=null){
                users = JSON.parse(users_str);
            }
            
          
            let name = document.getElementById("fullname").value;
            let username = document.getElementById("username").value;
            let password= document.getElementById("password").value;
            let cpassword = document.getElementById("cpassword").value;
            if(!regName.test(name)){
              alert('Invalid name given.');
            }
            else if(cpassword!=password){
               alert('Invalid password entered.');
            }
            else{
              let user_obj = { name,username,password}
              users.push(user_obj);
              console.log(users);

              
              localStorage.setItem("users",JSON.stringify(users));
              alert("Successfully Registered");
              window.location="/register";   
            }
                  
        }

    }
};
</script>

<style scoped>
</style>