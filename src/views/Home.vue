<template>
  <div class="home">
    <Navbar />
    <br>
    <br>
    <div className="bg-holder">
        <div className="jumbotron vertical-align">
          <div className="container white-text">
            <h1 class="display-4">Hello, Everyone!</h1>
            <p class="lead">
              This is a place for students who are interested in learning can
              find there best courses to brighten there future.
            </p>
            <hr class="my-4" />
            <p>
              To start learning, Click the Register Button to upload your
              Student Porfolio.
            </p>
            <p class="lead">
              <a class="btn btn-primary btn-lg" href="/register" role="button">
                Register
              </a>
            </p>
          </div>
        </div>
      </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "../components/Navbar.vue";

export default {
  name: "Home",
  components: {
    Navbar,
  },
};
</script>
<style scoped>
.home{
 display: flex;
 flex-direction: column;
}

.bg-holder{
  height: calc(100vh - 60px) !important;
  /* background-image: url("http://localhost:8080/img/educate.jpg"); */
 background-size: cover;
}

.vertical-align{
  min-height: calc(100vh - 60px) !important;
  display: flex;
  align-items: center;
}

.white-text{
  color: #fff !important;
}
.jumbotron{
  background: "#ededed !important";
}
</style>