<template>
  <div class="footer-sec">
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
            <div class="row content">
              <div class="col-21">
                <div class="logo-wrap">
                  <img class="img-fluid logo" src="../assets/image/owiro.png" alt="logo" />
                </div>
              </div>
              <div class="col-12 col-md-7 col-lg-7">
                <div class="row">
                  <div class="col-12 col-md-6 col-lg-6">
                    <div class="contact-info" v-for="(info, index) in contact" :key="index">
                      <ul>
                        <li class="info" v-for="(value, key) in info" :key="key">{{ key }}: <a href="#">{{ value }}</a>
                        </li>
                      </ul>
                    </div>
                  </div>
                  <div class="col-12 col-md-3 col-lg-3">
                    <div class="footer-primary">
                      <ul>
                        <li><a href="#">Main Home</a></li>
                        <li><a href="#">Contact</a></li>
                        <li><a href="#">Portfolio</a></li>
                        <li><a href="#">Landing</a></li>
                      </ul>
                    </div>
                  </div>
                  <div class="col-12 col-md-3 col-lg-3">
                    <div class="footer-secondary">
                      <ul>
                        <li><a href="#">About Us</a></li>
                        <li><a href="#">Our Team</a></li>
                        <li><a href="#">Our Process</a></li>
                      </ul>
                    </div>
                  </div>
                </div>
              </div>
              <div class="col-12 col-md-5 col-lg-5">
                <div class="newsletter">
                  <h3 class="title">Our Newsletter</h3>
                </div>
              </div>
            </div>
            <div class="copyright">
              <p>©Copyright {{ currentYear }} <a href="https://owirodigital.com/">Owiro Digital</a> All Rights Reserved</p>
            </div>
        </div>
    </footer>
  </div>
  </template>
  
  <script>
  
  export default {
    name: 'App',
    data() {
      return {
        currentYear: new Date().getFullYear(),
        scTimer: 0,
        scY: 0,
        contact: [
        {
          address: '471/B/07 Wakwella Road, Kalegana, Galle',
          phone: '+94 77 830 9497',
          email: 'letstalk@owirodigital.com'
        }
        ],
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
    padding-top: 120px;
    padding-bottom: 60px;

    .content{
      padding-bottom: 72px;
    }

    .copyright{
      padding-bottom: 20px;
      p{
        margin: 0;
        text-align: left;
        color: $color-2;

        a{
          text-decoration: none;
          color: $color-2;
          transition: all 0.3s;

          &:hover{
            color: #fff;
          }
        }
    }
    }

    .logo-wrap{
      .logo{
        width: 180px;
        padding-bottom: 30px;
      }
    }

    ul{
      padding-left: 0;
      padding-top: 25px;

      li{
        list-style: none;
        text-decoration: none;
        font-size: 13px;
        text-transform: uppercase;
        letter-spacing: .1em;
        font-weight: 500;
        color: #fff;

        padding-bottom: 6px;

        &.info{
          text-decoration: none;
          font-family: $font-2;
          font-size: 13px;
          text-transform: uppercase;
          letter-spacing: .1em;
          font-weight: 500;
          color: #fff;
          a{
            text-decoration: none;
            font-size: 13px;
            text-transform: uppercase;
            letter-spacing: .1em;
            font-weight: 500;
            color: #fff;
          }
        }

        a{
          text-decoration: none;
          font-size: 13px;
          text-transform: uppercase;
          letter-spacing: .1em;
          font-weight: 500;
          color: #fff;
        }
      }
    }

    .newsletter{
      .title{
        font-weight: 600;
          color: #ffffff;
          font-size: 30px;
          line-height: 1.16em;
          font-family: $font-1;
      }
    }
}
</style>
  