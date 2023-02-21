<template>
  <div class="Navigation">
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
              <router-link class="nav-link" :to="{ name: 'Home' }" v-scroll @click="closeMobileMenu"
                >Home</router-link
              >
            </li>
            <li class="nav-item">
              <router-link class="nav-link" :to="{ name: 'About' }" v-scroll @click="closeMobileMenu"
                >About</router-link
              >
            </li>
            <li class="nav-item">
              <router-link class="nav-link" :to="{ name: 'Blog' }" v-scroll @click="closeMobileMenu"
                >Blog</router-link
              >
            </li>
            <li class="nav-item">
              <router-link class="nav-link" :to="{ name: 'Clients' }" v-scroll @click="closeMobileMenu"
                >Client</router-link
              >
            </li>
            <li class="nav-item">
              <router-link class="nav-link" :to="{ name: 'Contact' }" v-scroll @click="closeMobileMenu"
                >Contact</router-link
              >
            </li>
            <li class="nav-item">
              <router-link class="nav-link" :to="{ name: 'Service' }" v-scroll @click="closeMobileMenu"
                >Service</router-link
              >
            </li>
            <li class="nav-item">
              <router-link class="nav-link" :to="{ name: 'Team' }" v-scroll @click="closeMobileMenu"
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
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 24 24"
                  width="24"
                  height="24"
                >
                  <path fill="none" d="M0 0h24v24H0z" />
                  <path d="M3 4h18v2H3V4zm6 7h12v2H9v-2zm-6 7h18v2H3v-2z" />
                </svg>
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
              <h2 class="title">Incredible and modern Company</h2>
              <p class="info">Contemporary theme especially made for technology & software developing company websites. Deon, a new age of WP design.</p>
              <ul class="contact">
                <li>
                  <a href="mailto:letstalk@owirodigital.com">letstalk@owirodigital.com</a>
                </li>
              </ul>
              <div class="sm">
                <ul>
                  <li><a href="#">Facebook</a></li>
                  <li><a href="#">Twitter</a></li>
                  <li><a href="#">Linkdin</a></li>
                </ul>
              </div>
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
  mounted() {
    const navbar = document.querySelector('.navbar-collapse');
    const navLinks = navbar.querySelectorAll('.nav-link');
    const navbarToggler = document.querySelector('.navbar-toggler');

    navLinks.forEach(link => {
      link.addEventListener('click', () => {
        if (navbar.classList.contains('show')) {
          navbarToggler.click();
        }
      });
    });
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

  .navbar-nav {
    display: flex;
    align-items: center;
    gap: 18px;

    @media only screen and (max-width: 768px) {
      padding-top: 20px;
    }

    .nav-item {
      @media only screen and (max-width: 768px) {
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
        position: relative;

        padding-left: 0px !important;
        padding-right: 0px !important;
        padding-bottom: 0px !important;
        padding-top: 0 !important;

        &::after {
          content: "";
          position: absolute;
          bottom: -5px;
          left: 0;
          right: 0;
          width: 100%;
          height: 2px;
          transform: scaleX(0);
          background-color: #000;
          transition: transform 0.3s;
        }

        &:hover::after {
          transform: scaleX(1);
        }

        @media only screen and (max-width: 768px) {
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

.offnav{
  .offcanvas{
    padding-left: 40px;
    padding-right: 15px;
    @media only screen and (max-width: 576px){
      padding-left: 0;
      padding-right: 0;
    }
    .offcanvas-body{
      .title{
        font-family: $font-1;
        font-weight: 600;
        color: #000;
        font-size: 35px;
        line-height: 1.14em;
        margin: 25px 0;
      }
      .info{
        margin-top: 15px;
        font-size: 18px;
        font-weight: 400;
      }
      .contact{
        padding-left: 0;
        li{
          list-style: none;
          a{
            background-image: -webkit-linear-gradient(5deg,#5cc3ee 0,#5d91ef 29%,#5e5ef0 50%,#947be1 73%,#ca97d2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-size: 18px;
          }
        }
      }

      .sm{
        padding-top: 30px;
        ul{
          padding-left: 0;
          li{
            list-style: none;
            a{
              text-decoration: none;
              position: relative;
              font-family: $font-2;
              font-size: 13px;
              font-weight: 500;
              line-height: 1.22em;
              text-transform: uppercase;
              letter-spacing: .2em;
              color: #000;

              &:hover{
                background-image: -webkit-linear-gradient(45deg,#5cc3ee 0,#5d91ef 29%,#5e5ef0 50%,#947be1 73%,#ca97d2 100%);
                -webkit-background-clip: text;
                -webkit-text-fill-color: transparent;
              }
            }
          }
        }
      }
    }
  }
}
</style>