<template>
  <div class="about">
    <section class="top">
      <div class="container">
        <h1 class="title">About Us</h1>
      </div>
    </section>

    <section class="who-we-are">
      <div class="container">
        <div class="row d-flex align-items-center">
          <div class="col-12 col-md-6 col-lg-6">
            <div class="right-bg">
              <img class="img-fluid" src="../assets/image/about/About-us-img-1.jpg" alt="image">
            </div>
          </div>
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
            </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="brands">
      <div class="container">
        <div class="row d-flex align-items-center">
          <div class="col-12 col-md-6 col-lg-6">
            <div class="wrapper">
              <div class="title">
              <span>WHO WE ARE</span>
              <h2 class="info">Network Structure Design</h2>
            </div>
            <div class="content">
              <!-- TabPane -->
              <div>
                <ul class="nav nav-tabs">
                  <li class="nav-item" v-for="tab in tabs" :key="tab.id">
                    <span
                      class="nav-link"
                      :class="{ active: tab.isActive }"
                      href="#"
                      @click="selectTab(tab)"
                    >
                      {{ tab.name }}
                    </span>
                  </li>
                </ul>
                <div class="tab-content" v-for="tab in tabs" :key="tab.id">
                  <div
                    :class="{ 'tab-pane': true, active: tab.isActive }"
                    v-html="tab.content"
                  ></div>
                </div>
              </div>
            </div>
            </div>
          </div>
          <div class="col-12 col-md-6 col-lg-6">
            <div class="right-bg">
              <img class="img-fluid" src="../assets/image/about/About-us-img-1.jpg" alt="image">
            </div>
          </div>
        </div>
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
      tabs: [
        {
          name: "Design",
          content: "Ut enim ad minim veniam, quis nostrud exercitation ullamconisi ut aliquip ex ea commodo Duis aute irure euripidis ne mel, mel lobortis viverra nulla varius laoreet.",
          isActive: true,
        },
        {
          name: "Marketing",
          content: "Tab 2 ContenLorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod reus tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam.",
        },
        {
          name: "Devs",
          content: `
          <p>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod reus tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam.
          </p>
          <ul><li>Point</li></ul>
          `,
        },
      ],
    };
  },
  methods: {
    selectTab(selectedTab) {
      this.tabs.forEach((tab) => {
        tab.isActive = tab.name === selectedTab.name;
      });
    },
  },
}
</script>


<style lang="scss" scoped>
//Variables
$color-1: #000;

$font-1 : 'Syne', sans-serif;
$font-2 : 'Heebo', sans-serif;
.about{
  .top{
    padding-top: 60px;
    padding-bottom: 60px;
    .title{
      text-align: center;
      color: #9e9e9e;
      margin: 0;
    background: linear-gradient(-120deg,rgba(202,151,210,.94),rgba(94,94,240,.94) 46%,rgba(92,195,238,.94));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    font-size: 60px;
    line-height: 1.1em;
    font-weight: 600;
    }
  }

  //Style Who we are section
  .who-we-are{
    position: relative;
    padding-top: 80px;
    //Left Side
    .wrapper{
      max-width: 360px;
      padding-left: 10%;
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
      }
    }
    .content{
      text-align: left;
      margin-top: 22px;

      p{
        font-family: $font-2;
        font-size: 18px;
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
    }

    .section-who-we-mark{
      position: absolute;
      left: 40px;
      bottom: 20px;
      z-index: 100;
      display: flex;
      align-items: center;

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
    }
    }
  }
  //Style Brands section
  .brands{
    position: relative;
    padding-top: 80px;
    //Left Side
    .wrapper{
      max-width: 360px;
      padding-left: 10%;
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
      }
    }
    .content{
      text-align: left;
      margin-top: 22px;

      p{
        font-family: $font-2;
        font-size: 18px;
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
    }

    .section-who-we-mark{
      position: absolute;
      left: 40px;
      bottom: 20px;
      z-index: 100;
      display: flex;
      align-items: center;

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
    }
    }
  }
}
</style>