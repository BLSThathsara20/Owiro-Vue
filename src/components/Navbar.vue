<template>
  <div class="nav">
    <div class="container">
      <nav class="navbar navbar-expand-lg bg-none">
        <a class="navbar-brand mr-auto" href="#">
          <img class="img-fluid" src="../assets/image/owiro.png" alt="logo" />
        </a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div
          class="collapse navbar-collapse justify-content-end"
          id="navbarSupportedContent"
        >
          <ul class="navbar-nav mb-2 mb-lg-0">
            <li class="nav-item">
              <router-link class="nav-link" :to="{ name: 'Home' }" v-scroll
                >Home</router-link
              >
            </li>
            <li class="nav-item">
              <router-link class="nav-link" :to="{ name: 'About' }" v-scroll
                >About</router-link
              >
            </li>
            <li class="nav-item">
              <router-link class="nav-link" :to="{ name: 'Blog' }" v-scroll
                >Blog</router-link
              >
            </li>
            <li class="nav-item">
              <router-link class="nav-link" :to="{ name: 'Clients' }" v-scroll
                >Client</router-link
              >
            </li>
            <li class="nav-item">
              <router-link class="nav-link" :to="{ name: 'Contact' }" v-scroll
                >Contact</router-link
              >
            </li>
            <li class="nav-item">
              <router-link class="nav-link" :to="{ name: 'Service' }" v-scroll
                >Service</router-link
              >
            </li>
            <li class="nav-item">
              <router-link class="nav-link" :to="{ name: 'Team' }" v-scroll
                >Team</router-link
              >
            </li>
            <li class="nav-item ps-4">
              <a
                class="btn"
                data-bs-toggle="offcanvas"
                href="#offcanvasExample"
                role="button"
                aria-controls="offcanvasExample"
              >
              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path fill="none" d="M0 0h24v24H0z"/><path d="M3 4h18v2H3V4zm6 7h12v2H9v-2zm-6 7h18v2H3v-2z"/></svg>
              </a>
            </li>
          </ul>
        </div>
      </nav>

      <!-- Add OffCanves Navigation -->
      <div class="offnav">
        <div
          class="offcanvas offcanvas-end"
          tabindex="-1"
          id="offcanvasExample"
          aria-labelledby="offcanvasExampleLabel"
        >
          <div class="offcanvas-header">
            <h5 class="offcanvas-title" id="offcanvasExampleLabel">
              Incredible and modern Company
            </h5>
            <button
              type="button"
              class="btn-close"
              data-bs-dismiss="offcanvas"
              aria-label="Close"
            ></button>
          </div>
          <div class="offcanvas-body">
            <div>
              Some text as placeholder. In real life you can have the elements
              you have chosen. Like, text, images, lists, etc.
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
  
  <script>

export default {
  name: "Navigation",
  data() {
    return {};
  },
};
</script>
  
  
  <style lang="scss">
//Variables
$font-1: "Syne", sans-serif;
$font-2: "Heebo", sans-serif;

.navbar {
  .navbar-brand {
    img {
      height: 46px;
    }
  }
}

nav {
    padding-top: 20px;

    .navbar-nav{
        display: flex;
        align-items: center;

        @media only screen and (max-width: 768px){
          padding-top: 20px;
        }

        .nav-item {
          @media only screen and (max-width: 768px){
            padding: 0 !important;
          }

          .nav-link {
            font-family: $font-2;
            font-size: 13px;
            text-transform: uppercase;
            letter-spacing: 0.2em;
            line-height: 1.23em;
            color: #1b1b1b;
            font-weight: 600;
            transition: all 0.3s;

            padding-left: 25px !important;
            padding-bottom: 0 !important;
            padding-top: 0 !important;

            @media only screen and (max-width: 768px){
              padding-left: 0px !important;
              padding-bottom: 8px !important;
            padding-top: 8px !important;
            }

            &.router-link-exact-active {
              display: inline-block;
              background: linear-gradient(
                -90deg,
                #5cc2ed 0,
                #5d62ee 50%,
                #c298d3 100%
              );
              background: -moz-linear-gradient(
                -90deg,
                #5cc2ed 0,
                #5d62ee 50%,
                #c298d3 100%
              );
              -webkit-background-clip: text;
              -webkit-text-fill-color: transparent;
            }
            &.router-link-active {
              background: linear-gradient(
                -90deg,
                #5cc2ed 0,
                #5d62ee 50%,
                #c298d3 100%
              );
              background: -moz-linear-gradient(
                -90deg,
                #5cc2ed 0,
                #5d62ee 50%,
                #c298d3 100%
              );
              -webkit-background-clip: text;
              -webkit-text-fill-color: transparent;
            }

            &:hover {
              background: linear-gradient(
                -90deg,
                #5cc2ed 0,
                #5d62ee 50%,
                #c298d3 100%
              );
              background: -moz-linear-gradient(
                -90deg,
                #5cc2ed 0,
                #5d62ee 50%,
                #c298d3 100%
              );
              -webkit-background-clip: text;
              -webkit-text-fill-color: transparent;
            }
          }
  }
    }
}
</style>