<template>
    <div class="back-to-top">
        <div id="app" v-cloak>
            <transition name="fade">
                <div id="pagetop" class="fixed right-0 bottom-0" v-show="scY > 300" @click="toTop">
                    <span>
                        Back to top
                    </span>
                    <div class="line"></div>
                </div>
            </transition>
        </div>
    </div>

    <!-- Final Section -->
    <section class="final-section">
      <div class="container-fluid">
        <div class="row">
          <div class="col-12 col-md-6 -col-lg-6 left-bg">
            <div class="wrapper">
              <div class="content">
                <h5 class="title">Join Our Team</h5>
                <p>
                  Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudanti.
                </p>
              </div>
              <div class="action">
                <a href="#">
                  <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="90px" height="90px" viewBox="0 0 90 90" enable-background="new 0 0 90 90" xml:space="preserve">
                  <circle fill="none" stroke="#C3C4F9" stroke-width="2" stroke-miterlimit="10" cx="45.567" cy="44.925" r="42"></circle>
                  <g>
                    <path d="M51.662,45.394L40.958,56.019l-1.016-0.938l10.235-10.156L40.021,34.769l0.938-0.938l10.704,10.625V45.394z"></path>
                  </g>
                  </svg>
                </a>
              </div>
            </div>
          </div>
          <div class="col-12 col-md-6 -col-lg-6 right-bg">
            <div class="wrapper">
              <div class="content">
                <h5 class="title">Join Our Team</h5>
                <p>
                  Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudanti.
                </p>
              </div>
              <div class="action">
                <a href="#">
                  <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="90px" height="90px" viewBox="0 0 90 90" enable-background="new 0 0 90 90" xml:space="preserve">
                  <circle fill="none" stroke="#C3C4F9" stroke-width="2" stroke-miterlimit="10" cx="45.567" cy="44.925" r="42"></circle>
                  <g>
                    <path d="M51.662,45.394L40.958,56.019l-1.016-0.938l10.235-10.156L40.021,34.769l0.938-0.938l10.704,10.625V45.394z"></path>
                  </g>
                  </svg>
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <footer>
        <div class="container">
            <p>©Copyright 2023 <a href="https://owirodigital.com/">Owiro Digital</a> All Rights Reserved</p>
        </div>
    </footer>
  </template>
  
  <script>
  
  export default {
    name: 'App',
    data() {
      return {
        scTimer: 0,
        scY: 0,
      }
    },
    mounted() {
      window.addEventListener('scroll', this.handleScroll);
    },
    methods: {
      handleScroll: function () {
        if (this.scTimer) return;
        this.scTimer = setTimeout(() => {
          this.scY = window.scrollY;
          clearTimeout(this.scTimer);
          this.scTimer = 0;
        }, 100);
      },
      toTop: function () {
        window.scrollTo({
          top: 0,
          behavior: "smooth"
        });
      },
    },
  }
  </script>

<style lang="scss">
//Variables
$color-1: #1b1b1b;
$color-2: #7c7c7c;

$font-1 : 'Syne', sans-serif;
$font-2 : 'Heebo', sans-serif;

.back-to-top{
    

    #app{
        transform: rotate(-90deg);
        position: fixed;
        bottom: 80px;
        right: 30px;
        cursor: pointer;

        .line{
            width: 80px;
            height: 1px;
            background-color: #9f9f9f;
        }
    }
}

//Style Final Section
.final-section{
    .left-bg{
      background-image: linear-gradient(60deg,rgba(202,151,210,.25) 0,rgba(148,123,225,.25) 17%,rgba(94,94,240,.25) 45%,rgba(93,145,239,.25) 83%,rgba(92,195,238,.25) 100%);
      
      &::before{
        background-image: radial-gradient(circle,rgba(92,195,238,.5) 0,rgba(92,195,238,.375) 12.5%,rgba(92,195,238,.25) 25%,rgba(92,195,238,.125) 37.5%,rgba(92,195,238,0) 50%);
      }
    }
    .right-bg{
      background-color: #F3F3F3;
    }
    .wrapper{
        padding-left: 15%;
        padding-top: 100px;
        padding-bottom: 100px;

        display: flex;
        align-items: center;
        gap: 20px;

        .content{
          .title{
            font-weight: 600;
            color: $color-1;
            font-size: 40px;
            line-height: 1.05em;
            word-break: break-word;
          }
          p{
            margin-top: 20px;
            font-size: 16px;
            font-family: $font-2;
            color: $color-1;
          }
        }

        .action{
          a{
            padding-right: 12px;
          }
        }
      }
  }

footer{
    background-color: $color-1;
    padding-top: 40px;
    padding-bottom: 40px;
    p{
        margin: 0;
        text-align: left;
        color: $color-2;
    }
}
</style>
  