<template>
  <div class="container">
    <nav class="navbar navbar-expand-lg bg-none">
      <div class="container-fluid">
        <a class="navbar-brand mr-auto" href="#">
          <img class="img-fluid" src="./assets/image/owiro.png" alt="logo">
        </a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse justify-content-end" id="navbarSupportedContent">
          <ul class="navbar-nav mb-2 mb-lg-0">
            <li class="nav-item"><router-link class="nav-link" :to="{name : 'Home'}" v-scroll>Home</router-link></li>
          <li class="nav-item"><router-link class="nav-link" :to="{name : 'About'}" v-scroll>About</router-link></li>
          <li class="nav-item"><router-link class="nav-link" :to="{name : 'Blog'}" v-scroll>Blog</router-link></li>
          <li class="nav-item"><router-link class="nav-link" :to="{name : 'Clients'}" v-scroll>Client</router-link></li>
          <li class="nav-item"><router-link class="nav-link" :to="{name : 'Contact'}" v-scroll>Contact</router-link></li>
          <li class="nav-item"><router-link class="nav-link" :to="{name : 'Service'}" v-scroll>Service</router-link></li>
          <li class="nav-item"><router-link class="nav-link" :to="{name : 'Team'}" v-scroll>Team</router-link></li>
          </ul>
        </div>
      </div>
    </nav>
  </div>
  <router-view/>
  <Footer/>
</template>

<script>
// @ is an alias to /src
import Footer from '@/components/Footer.vue'

export default {
  name: 'HomeView',
  components: {
    Footer,
  }
}
</script>


<style lang="scss">

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

.navbar{
  .navbar-brand{
    img{
      height: 46px;
    }
  }
}

nav {
  .nav-item {

    .nav-link{
      color: #2c3e50;
      transition: all 0.3s;

      &.router-link-exact-active {
        display: inline-block;
    background: linear-gradient(-90deg,#5cc2ed 0,#5d62ee 50%,#c298d3 100%);
    background: -moz-linear-gradient(-90deg,#5cc2ed 0,#5d62ee 50%,#c298d3 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
      }
      &.router-link-active{
        display: inline-block;
    background: linear-gradient(-90deg,#5cc2ed 0,#5d62ee 50%,#c298d3 100%);
    background: -moz-linear-gradient(-90deg,#5cc2ed 0,#5d62ee 50%,#c298d3 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
      }

      &:hover{
        display: inline-block;
    background: linear-gradient(-90deg,#5cc2ed 0,#5d62ee 50%,#c298d3 100%);
    background: -moz-linear-gradient(-90deg,#5cc2ed 0,#5d62ee 50%,#c298d3 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
      }
    }
  }
}
</style>
