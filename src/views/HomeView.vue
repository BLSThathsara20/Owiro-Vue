<template>
  <div class="home">
    <div class="gradient-coner"></div>
    <div class="gradient-coner-left"></div>
    <div id="line-navigation"></div>
    <div class="keep-scroll">
      <span id="line-navigation-keep-scroll"></span>
      <span>Keep Scrolling</span>
    </div>

    <!-- Add Hero Slider -->
    <HeroSlider/>
    
    <section class="who-we-are">
      <div class="container">
        <div class="row d-flex align-items-center">
          <div class="col-12 col-md-6 col-lg-6">
            <div class="wrapper">
              <div class="title">
              <span>WHO WE ARE</span>
              <h2 class="info">Network Structure Design</h2>
            </div>
            <div class="content">
              <p>
                Aliquam lorem ante, dapibus in, viverra quis, feugiat a, tellus. Phasellus sapien nulla ut metus varius laoreet. Quisque rutrum. Aenean imperdiet. Etiam ultricies nisi vel augue. Curabitur ullamcorper ultricies nisi. Nam eget dui. Maecenas nec odio et ante tincidunt tempus vitae
              </p>
              <p>
                Aliquam lorem ante, dapibus viverra quis feugiat a, tellus. Phasellus nisi vel augue. nulla ut metus varius laoreet. Quisque rutrum. Aenean imperdiet.
              </p>
            </div>
            </div>
          </div>
          <div class="col-12 col-md-6 col-lg-6">
            <div class="right-bg">
              <img class="img-fluid" src="../assets/image/Main-home-img-1.png" alt="image">
            </div>
          </div>
        </div>
      </div>
      <div class="section-who-we-mark">
        <span id="line-navigation-who-we"></span>
        <span>Who We Are</span>
      </div>
    </section>

    <section class="how-it-works">
      <div class="container">
        <div class="row d-flex align-items-center">
          <div class="col-12 col-md-6 col-lg-6 order-1 order-md-0">
            <div class="img-wrapper">
              <img class="img-fluid" :src="works[currentImageIndex].src" />
            </div>
          </div>
          <div class="col-12 col-md-6 col-lg-6 order-0 order-md-1">
            <div class="wrapper">
              <div class="top">
                <span class="sub-title">how it works</span>
                <h3 class="title">Network Infrastructure Design</h3>
              </div>
            </div>
            <ul class="work-list">
              <li
                class="work-item"
                v-for="(work, index) in works"
                v-bind:key="index"
                v-bind:class="{ active: index === currentImageIndex }"
                v-on:mouseenter="changeImage(index)"
              >
              <router-link :to="`/work/${index + 1}`" v-scroll-to="{ element: '#single-work', offset: -60 }"><span>{{ work.name }}</span></router-link>
              </li>
            </ul>
          </div>
        </div>
    </div>
    <div class="section-how-it-works">
        <span id="line-navigation-who-we"></span>
        <span>Read Our News</span>
      </div>
    </section>

    <!-- Services Section -->
    <section class="services">
      <div class="container">
        <div class="row">
          <div class="col-12 col-md-4 col-lg-4" v-for="(service, index) in services" v-bind:key="index">
            <div class="content-wrapper">
              <span class="bg-text">{{service.number}}</span>
              <h4 class="title">
                <a href="#">{{service.name}}</a>
              </h4>
              <p class="description">
                {{service.description}}
              </p>
              <div class="action">
                <a href="#">View More</a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Articles Section -->
    <section class="articles">
      <div class="container">
        <div class="row g-0">
          <div class="col-12 col-md-4 col-lg-4">
            <div class="wrapper">
              <div class="overlay"></div>
              <h3 class="title"><a href="#">Smart Teck</a></h3>
            </div>
          </div>
          <div class="col-12 col-md-4 col-lg-4">
            <div class="wrapper">
              <div class="overlay"></div>
              <h3 class="title"><a href="#">Smart Teck</a></h3>
            </div>
          </div>
          <div class="col-12 col-md-4 col-lg-4">
            <div class="wrapper">
              <div class="overlay"></div>
              <h3 class="title"><a href="#">Smart Teck</a></h3>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Partners Section -->
    <section class="parters">
      <div class="container">
        <div class="row">
          <div class="col-12 col-md-4 col-lg-4">
            <div class="wrapper">
              <span>Partners</span>
              <h3 class="title">Trusted and Supported by Many</h3>
              <p>
                Ut enim ad minim veniam, quis nostrud exercitation ullamconisi ut aliquip ex
              </p>
              <div class="action">
                <a href="#">View More</a>
              </div>
            </div>
          </div>
          <div class="col-12 col-md-8 col-lg-8">
            <div class="row">
              <div class="col-6 col-md-4 col-lg-4" v-for="(partner, index) in partners" v-bind:key="index">
                <div class="logo-wrapper">
                  <h5 class="name"><a href="#">{{partner.name}}</a></h5>
                  <img class="img-fluid" v-bind:src="partner.logo" alt="">
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="section-partners-mark">
        <span id="line-navigation-who-we"></span>
        <span>Meet Our Clients</span>
      </div>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src
import HeroSlider from '@/components/HeroSlider.vue'


export default {
  name: 'HomeView',
  components: {
    HeroSlider,
  },
  data() {
    return {
      works: [
      { 
        name: 'Fast And Easy', 
        src: require('@/assets/image/Main-home-how-it-01.jpg'),
        description: 'This is a description of Work 1',
        images: [
          require('@/assets/image/Main-home-how-it-01.jpg'),
          require('@/assets/image/Main-home-how-it-01.jpg'),
          require('@/assets/image/Main-home-how-it-01.jpg')
        ]
      },
      { 
        name: 'Safe Online Service', 
        src: require('@/assets/image/Main-home-how-it-02.jpg'),
        description: 'This is a description of Work 2',
        images: [
          require('@/assets/image/Main-home-how-it-01.jpg'),
          require('@/assets/image/Main-home-how-it-02.jpg'),
          require('@/assets/image/Main-home-how-it-01.jpg')
        ]
      },
      { 
        name: 'Modern Look', 
        src: require('@/assets/image/Main-home-how-it-01.jpg'),
        description: 'This is a description of Work 3',
        images: [
          require('@/assets/image/Main-home-how-it-01.jpg'),
          require('@/assets/image/Main-home-how-it-02.jpg'),
          require('@/assets/image/Main-home-how-it-01.jpg')
        ]
      },
      { 
        name: 'Reliable Usage', 
        src: require('@/assets/image/Main-home-how-it-01.jpg'),
        description: 'This is a description of Work 3',
        images: [
          require('@/assets/image/Main-home-how-it-01.jpg'),
          require('@/assets/image/Main-home-how-it-02.jpg'),
          require('@/assets/image/Main-home-how-it-01.jpg')
        ]
      },
    ],
    services: [
      {
        name: 'Manage your data efficiently', 
        description: 'Lorem ipsum dolor sit amet ridiculus consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Montes est massa. Cum sociis Theme natoq',
        number: '01',
      },
      {
        name: 'Built with neat utility features', 
        description: 'Lorem ipsum dolor sit amet ridiculus consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Montes est massa. Cum sociis Theme natoq',
        number: '02',
      },
      {
        name: 'Futuristic interactive designs', 
        description: 'Lorem ipsum dolor sit amet ridiculus consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Montes est massa. Cum sociis Theme natoq',
        number: '03',
      },
    ],
    partners: [
      {
        name: 'ANISHAJAYAKODY', 
        logo: require('@/assets/image/logos/ANISHAJAYAKODY.png'),
      },
      {
        name: 'CARESRILANKA', 
        logo: require('@/assets/image/logos/CARESRILANKA.png'),
      },
      {
        name: 'CEYLONIAN PICTURES', 
        logo: require('@/assets/image/logos/CEYLONIAN PICTURES.png'),
      },
      {
        name: 'MAGGIE', 
        logo: require('@/assets/image/logos/MAGGIE.png'),
      },
    ],
      currentImageIndex: 0,
    };
  },
  methods: {
    changeImage(index) {
      this.currentImageIndex = index;
    },
  },
}
</script>

<style lang="scss" scoped>
//Variables
$slider-line: linear-gradient(45deg,#5cc3ee 0,#5d91ef 29%,#5e5ef0 50%,#947be1 73%,#ca97d2 100%);
$color-1: #000;

$font-1 : 'Syne', sans-serif;
$font-2 : 'Heebo', sans-serif;


//Style Gradient Coner
.gradient-coner:before {
    content: "";
    z-index: -1;
    position: absolute;
    top: -20px;
    right: 0;
    width: 40%;
    height: 50%;
    border-bottom-left-radius: 80%;
    background: linear-gradient(-45deg,  #7bdef250 20%, #f2b5d485 100% );
    transform: translate3d(0px, 20px, 0) scale(1);
    filter: blur(70px);
    opacity: var(0.3);
    transition: opacity 0.3s;
    overflow: hidden;
}

/* 
* Prevents issues when the parent creates a 
* stacking context. (For example, using the transform
* property )
*/
.gradient-coner::after {
    content: "";
    z-index: -1;
    position: absolute;
    top: 0;
    right: 0;
    background: inherit;
    border-radius: inherit;
    overflow: hidden;
}
//Style Gradient Coner Left
.gradient-coner-left:before {
    content: "";
    z-index: -1;
    position: absolute;
    bottom: -20px;
    left: 0;
    width: 30%;
    height: 60%;
    border-top-right-radius: 80%;
    background: linear-gradient(-45deg,  #7bdef250 20%, #f2b5d485 100% );
    transform: translate3d(0px, 20px, 0) scale(1);
    filter: blur(120px);
    opacity: var(0.2);
    transition: opacity 0.3s;
    overflow: hidden;
}

/* 
* Prevents issues when the parent creates a 
* stacking context. (For example, using the transform
* property )
*/
.gradient-coner-left::after {
    content: "";
    z-index: -1;
    position: absolute;
    bottom: 0;
    left: 0;
    background: inherit;
    border-radius: inherit;
    overflow: hidden;
}
        

  #line-navigation{
    display: block;
    position: fixed;
    top: 0;
    left: 40px;
    width: 1px;
    height: 100%;
    background: $slider-line;
    z-index: 99;

    @media only screen and (max-width: 576px){
      display: none;
    }
  }
  .keep-scroll{
    position: absolute;
    top: 90vh;
    left: 40px;
    z-index: 100;
    display: flex;
    align-items: center;

    @media only screen and (max-width: 576px){
           display: none;
        }

    #line-navigation-keep-scroll{
    border-left: 1px solid $color-1;
    height: 60px;
    }
    span{
      padding-left: 15px;
      font-size: 15px;
      line-height: 16px;
      max-width: 100px;
      display: block;
      text-align: left;
    }
  }

  //Style Who we are section
  .who-we-are{
    position: relative;
    padding-top: 80px;
    padding-bottom: 80px;

    @media only screen and (max-width: 768px){
      padding-top: 60px;
    padding-bottom: 60px;
        }
        @media only screen and (max-width: 576px){
          padding-top: 40px;
    padding-bottom: 40px;
        }
    //Left Side
    .wrapper{
      max-width: 360px;
      padding-left: 10%;

      @media only screen and (max-width: 768px){
        max-width: none;
      padding-left: 0;
      }
      
      .title{
      text-align: left;

      span{
        font-size: 13px;
        letter-spacing: 4px;
        line-height: 16px;
        color: #8a8a8a;
        text-transform: uppercase;
        font-weight: 500;
        font-family: Syne,sans-serif;
        margin-bottom: 7px;
      }
      .info{
        color: $color-1;
        font-size: 50px;
        line-height: 1.1em;

        margin-top: 10px;

        @media only screen and (max-width: 786px){
            font-size: 32px;
        }
          @media only screen and (max-width: 576px){
            font-size: 22px;
        }
      }
    }
    .content{
      text-align: left;
      margin-top: 22px;

      p{
        font-family: $font-2;
        font-size: 18px;

        @media only screen and (max-width: 786px){
            font-size: 14px;
        }
          @media only screen and (max-width: 576px){
            font-size: 14px;
        }
      }
    }
    }

    //Right Side
    .right-bg{
      background-image: url("../assets/image/Main-home-img-4.png");
      background-position: center;
      background-repeat: no-repeat;
      background-size: contain;

      display: flex;
      justify-content: center;

      @media only screen and (max-width: 576px){
        padding-top: 15px;
      }

      img{
        @media only screen and (max-width: 576px){
          height: 50vh;
        }
      }
    }

    .section-who-we-mark{
      position: absolute;
      left: 40px;
      bottom: 20px;
      z-index: 100;
      display: flex;
      align-items: center;

      @media only screen and (max-width: 576px){
           display: none;
        }

      #line-navigation-who-we{
        border-left: 1px solid $color-1;
        height: 60px;
      }
      span{
      padding-left: 15px;
      font-size: 15px;
      line-height: 16px;
      max-width: 66px;
      display: block;
      text-align: left;
      color: $color-1;

      @media only screen and (max-width: 786px){
            font-size: 12px;
        }
    }
    }
  }

  //Style How It Works Section
  .how-it-works{
    padding-top: 80px;
    padding-bottom: 80px;
    position: relative;

    @media only screen and (max-width: 768px){
      padding-top: 60px;
    padding-bottom: 60px;
        }
        @media only screen and (max-width: 576px){
          padding-top: 0px;
    padding-bottom: 40px;
        }
    .img-wrapper{
      overflow: hidden;

      @media only screen and (max-width: 768px){
          display: flex;
          justify-content: center;

          padding-top: 22px;
          padding-top: 35px;
        }
      img{
        width: 80%;
        scale: 1;

        @media only screen and (max-width: 576px){
          width: 75%;
        }
      }
    }

    .wrapper{
      @media only screen and (max-width: 576px){
      padding-top: 30px;
    }
      .top{
        text-align: left;
        .sub-title{
          font-size: 13px;
          letter-spacing: 4px;
          line-height: 16px;
          color: #8a8a8a;
          text-transform: uppercase;
          font-weight: 500;
          font-family: Syne,sans-serif;

          margin-bottom: 13px;
        }
        .title{
          color: #000;
          font-size: 50px;
          line-height: 1.1em;
          font-weight: 600;

          @media only screen and (max-width: 786px){
            font-size: 32px;
        }
          @media only screen and (max-width: 576px){
            font-size: 24px;
        }
        }
      }
    }
    .work-list{
      padding-top: 40px;

      @media only screen and (max-width: 576px){
      padding-left: 0;
    }
        .work-item{
          list-style: none;
          position: relative;
          margin-bottom: 40px;

          padding-left: 38px;

          @media only screen and (max-width: 768px){
          margin-bottom: 20px;
        }
        @media only screen and (max-width: 576px){
          margin-bottom: 12px;
        }
          
          &:hover{
            a{
              span{
                background-image: linear-gradient(-90deg,#c298d3 0,#5d62ee 25%,#5cc2ed 50%,currentColor 51%,currentColor 100%);
              -webkit-background-clip: text;
              -webkit-text-fill-color: transparent;
              background-size: 200% 100%;
              background-position: left;
              transition: background-position .4s ease;
              background-position: right;
              }
            }
          }

          &.active{
            a{
              &::before{
              content: '';
              position: absolute;
              left: 0;
              top: -5px;
              height: 100%;
              width: 1px;
              background: #000;
              transition: all .6s ease;
            }
            span{
                background-image: linear-gradient(-90deg,#c298d3 0,#5d62ee 25%,#5cc2ed 50%,currentColor 51%,currentColor 100%);
              -webkit-background-clip: text;
              -webkit-text-fill-color: transparent;
              background-size: 200% 100%;
              background-position: left;
              transition: background-position .4s ease;
              background-position: right;
              }
            }
          }

          a{
            display: block;
            transition: all 0.3s;
            text-decoration: none;
            text-align: left;

            span{
              text-align: left;
              background-image: linear-gradient(-90deg,#5cc2ed 0,#5d62ee 25%,#c298d3 50%,currentColor 51%,currentColor 100%);
              -webkit-background-clip: text;
              -webkit-text-fill-color: transparent;
              background-size: 200% 100%;
              background-position: left;
              transition: background-position .4s ease;
              background-position: right;
              transition: all 0.3s;

              font-size: 30px;
              font-weight: 600;
            }
          }
        }
      }

      //Style Section Mark
      .section-how-it-works{
      position: absolute;
      left: 40px;
      bottom: 20px;
      z-index: 100;
      display: flex;
      align-items: center;

          @media only screen and (max-width: 576px){
           display: none;
        }

      #line-navigation-who-we{
        border-left: 1px solid $color-1;
        height: 60px;
      }
      span{
      padding-left: 15px;
      font-size: 15px;
      line-height: 16px;
      max-width: 82px;
      display: block;
      text-align: left;
      color: $color-1;

      @media only screen and (max-width: 786px){
            font-size: 14px;
        }
          @media only screen and (max-width: 576px){
            font-size: 12px;
        }
    }
    }
  }

  //Style Services Section
  .services{
    padding-top: 160px;
    padding-bottom: 120px;

    @media only screen and (max-width: 768px){
      padding-top: 80px;
    padding-bottom: 25px;
        }
        @media only screen and (max-width: 576px){
          padding-top: 30px;
    padding-bottom: 15px;
        }
    .content-wrapper{
      position: relative;

      @media only screen and (max-width: 768px){
          padding-bottom: 110px;
        }
      @media only screen and (max-width: 576px){
          padding-bottom: 90px;
        }

      .bg-text{
        display: inline-block;
        background: linear-gradient(-90deg,#5cc2ed 0,#5d62ee 50%,#c298d3 100%);
        background: -moz-linear-gradient(-90deg,#5cc2ed 0,#5d62ee 50%,#c298d3 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;

        font-size: 230px;
        letter-spacing: 0;
        line-height: 1.2em;
        font-weight: 400;
        font-family: Syne,sans-serif;
        z-index: -2;
        position: absolute;
        left: -68px;
        top: -53%;
        opacity: .2;

        @media only screen and (max-width: 992px){
            left: 0;
            top: -36%;
        }
        @media only screen and (max-width: 576px){
            left: 0;
            top: -36%;
        }

        @media only screen and (max-width: 786px){
            font-size: 230px;
            left: 0;
            top: -42%;
        }
          
      }
      .title{
        a{
          text-decoration: none;
          color: $color-1;
          font-weight: 600;
          font-size: 35px;

          @media only screen and (max-width: 786px){
            font-size: 30px;
        }
        }
      }

      .description{
        font-size: 17px;
        margin: 16px 60px 0 0;
        font-family: $font-2;

        @media only screen and (max-width: 786px){
            font-size: 17px;
            margin-right: 0;
        }
          @media only screen and (max-width: 576px){
            font-size: 16px;
        }
      }

      .action{
        padding-top: 15px;

        a{
          cursor: pointer;
          text-decoration: none;
          color: $color-1;
          font-size: 16px;
          letter-spacing: 1.5px;
          text-transform: uppercase;

          color: #000;
          border: 0;
          padding: 0 0 0 95px !important;
          letter-spacing: .2em;
          background-color: transparent;
          transition: all .4s cubic-bezier(0,.68,.58,1);

          font-family: Archivo,sans-serif;
          font-size: 12px;
          line-height: 1.33em;
          letter-spacing: .2em;
          font-weight: 500;
          position: relative;
          display: inline-flex;
          vertical-align: middle;
          width: auto;
          margin: 0;
          text-decoration: none;
          text-transform: uppercase;
          border-radius: 0;
          outline: 0;
          transition: color .2s ease-out,background-color .2s ease-out,border-color .2s ease-out;
          padding: 17px 48px 15px 50px;
          transition: all 0.5s;

          @media only screen and (max-width: 786px){
            font-size: 14px;
        }

          &::before{
            content: '';
            display: table;
            table-layout: fixed;
          }

            &::after{

              content: '';
                position: absolute;
                top: 50%;
                left: 0;
                width: 80px;
                height: 1px;
                background-color: #57b8e0;
                transition: width .4s cubic-bezier(0,.68,.58,1);
            }

            &:hover{
              padding-left: 0px !important;
              &::after{

              content: '';
                width: 0;
              } 
            }
        }
      }
    }
  }

  //Styel Article Section
  .articles{
    padding-top: 80px;
    padding-bottom: 80px;

    @media only screen and (max-width: 768px){
      padding-top: 60px;
    padding-bottom: 60px;
        }
        @media only screen and (max-width: 576px){
          padding-top: 0px;
          padding-bottom: 40px;
        }
    .wrapper{
      position: relative;
      height: 70vh;
      background-image: url('../assets/image/Main-home-how-it-01.jpg');
      background-position: center;
      background-size: cover;
      background-repeat: no-repeat;

      @media only screen and (max-width: 768px){
        height: 50vh;
        }
        @media only screen and (max-width: 576px){
          height: 40vh;
        }

      .overlay{
        position: absolute;
        inset: 0;
        background-color: #ffffff00;
        height: 100%;
        z-index: 10;
        transition: all 0.3s;

        &:hover{
          background-color: #ffffffac;
        }
      }
      .title{
        z-index: 20;
        position: absolute;
        bottom: 15px;
        left: 15px;

        a{
          text-decoration: none;
          color: $color-1;
          font-weight: 600;
          font-size: 40px;
          line-height: 1.05em;

          background-image: linear-gradient(-90deg,#5cc2ed 0,#5d62ee 25%,#c298d3 50%,currentColor 51%,currentColor 100%);
          -webkit-background-clip: text;
          -webkit-text-fill-color: transparent;
          background-size: 200% 100%;
          background-position: left;
          transition: background-position .4s ease;

          @media only screen and (max-width: 786px){
            font-size: 34px;
        }
          @media only screen and (max-width: 576px){
            font-size: 24px;
        }

        }
      }
    }
  }

  //Style Partners Section
  .parters{
    padding-top: 80px;
    padding-bottom: 80px;
    position: relative;

    @media only screen and (max-width: 768px){
      padding-top: 60px;
    padding-bottom: 60px;
        }
        @media only screen and (max-width: 576px){
          padding-top: 40px;
    padding-bottom: 40px;
        }
    .wrapper{
      padding-bottom: 80px;
      @media only screen and (max-width: 576px){
    padding-bottom: 40px;
        }
      span{
        font-size: 13px;
        letter-spacing: 4px;
        line-height: 16px;
        color: #8a8a8a;
        text-transform: uppercase;
        font-weight: 500;
        font-family: $font-1;
        margin-bottom: 7px;
      }
      .title{
        font-size: 50px;
        color: $color-1;
        line-height: 1.2;
        font-weight: 600;

        @media only screen and (max-width: 786px){
            font-size: 34px;
        }
          @media only screen and (max-width: 576px){
            font-size: 22px;
        }
      }
      p{
        margin-top: 16px;
        font-size: 16px;
        font-family: $font-2;

        @media only screen and (max-width: 786px){
            font-size: 13px;
        }
      }
      .action{
        padding-top: 30px;
        a{
          text-decoration: none;
          padding: 10px 40px;
          color: #000;
          border: 1px solid;
          border-image-slice: 1;
          border-image-source: linear-gradient(70deg,#57b8e0,#5762e2,#be8ec6);
          background: none;
          transition: all 0.3s;

          &:hover{
            color: #fff;
            background: linear-gradient(45deg,#5cc3ee 0,#5d91ef 29%,#5e5ef0 50%,#947be1 73%,#ca97d2 100%);
          }
        }
      }
    }

    .logo-wrapper{
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;

      @media only screen and (max-width: 768px){
          padding-top: 20px;
        }

      &:hover{
        .name{
          opacity: 1;
        }
      }
      .name{
        background-color: #d0d0d0;
        text-align: center;
        padding: 8px 35px;
        min-height: 50px;
        display: flex;
        align-items: center;
        justify-content: center;
        transition: all 0.3s;
        opacity: 0;
        width: 100%;

        @media only screen and (max-width: 768px){
          opacity: 1;
        }
        a{
          text-decoration: none;
          font-weight: 400;
          letter-spacing: 1.3;
          color: $color-1;
          font-size: 14px;

          @media only screen and (max-width: 786px){
            font-size: 13px;
        }
          
        }
      }
    }

    //Style Section Mark
    .section-partners-mark{
      position: absolute;
      left: 40px;
      bottom: 20px;
      z-index: 100;
      display: flex;
      align-items: center;

      @media only screen and (max-width: 576px){
           display: none;
        }

      #line-navigation-who-we{
        border-left: 1px solid $color-1;
        height: 60px;
      }
      span{
      padding-left: 15px;
      font-size: 15px;
      line-height: 16px;
      max-width: 82px;
      display: block;
      text-align: left;
      color: $color-1;
    }
    }
  }
</style>