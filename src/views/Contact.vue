<template>
  <div class="contact">
    <section class="top">
      <div class="container">
        <h1 class="title">Contact Us</h1>
      </div>
    </section>

    <!-- Services Section -->
    <section class="info">
      <div class="container">
        <div class="row">
          <div class="col-12 col-md-4 col-lg-4" v-for="(singleInfo, index) in info" v-bind:key="index">
            <div class="content-wrapper">
              <h4 class="title">
                <a href="#">{{singleInfo.name}}</a>
              </h4>
              <p class="description">
                {{singleInfo.description}}
              </p>
              <div class="action">
                <a href="#">View More</a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="form-format">
      <div class="container">
        <div class="row">
          <div class="col-12 col-md-6 col-lg-6"></div>
          <div class="col-12 col-md-6 col-lg-6">
            <div class="form-wrapper">
              <form @submit.prevent="submitForm">
                <div>
                  <label for="name">Name:</label>
                  <input type="text" id="name" v-model="name" required>
                </div>
                <div>
                  <label for="email">Email:</label>
                  <input type="email" id="email" v-model="email" required>
                </div>
                <div>
                  <label for="message">Message:</label>
                  <textarea id="message" v-model="message" required></textarea>
                </div>
                <button type="submit">Submit</button>
                <div v-if="messageSent" class="success-message">Message sent!</div>
                <div v-if="errorMessage" class="error-message">{{ errorMessage }}</div>
            </form>
            </div>
          </div>
        </div>
      </div>
    </section>

  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'HomeView',
  components: {
    
  },
  data() {
    return {
      info: [
      {
        name: 'Manage your data efficiently', 
        description: 'Lorem ipsum dolor sit amet ridiculus consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Montes est massa. Cum sociis Theme natoq',
      },
      {
        name: 'Built with neat utility features', 
        description: 'Lorem ipsum dolor sit amet ridiculus consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Montes est massa. Cum sociis Theme natoq',
      },
      {
        name: 'Futuristic interactive designs', 
        description: 'Lorem ipsum dolor sit amet ridiculus consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Montes est massa. Cum sociis Theme natoq',
      },
    ],
    name: '',
    email: '',
    message: '',
    messageSent: false,
    errorMessage: '',
    };
  },
  methods: {
    submitForm() {
      if (!this.name || !this.email || !this.message) {
        this.errorMessage = 'Please fill in all fields.';
        return;
      }
      axios.post('/send-email', {
        name: this.name,
        email: this.email,
        message: this.message
      })
      .then(response => {
        this.messageSent = true;
        this.name = '';
        this.email = '';
        this.message = '';
        this.errorMessage = '';
      })
      .catch(error => {
        this.errorMessage = 'An error occurred while sending the message. Please try again later.';
      });
    }
  },
}
</script>


<style lang="scss" scoped>
//Variables
$color-1: #000;

$font-1 : 'Syne', sans-serif;
$font-2 : 'Heebo', sans-serif;

.contact{
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

  //Style Info Section
  .info{
    padding-top: 40px;
    padding-bottom: 40px;
    .content-wrapper{
      .title{
        a{
          text-decoration: none;
          color: $color-1;
          font-weight: 600;
          font-size: 35px;
        }
      }

      .description{
        font-size: 17px;
        margin: 16px 60px 0 0;
        font-family: $font-2;
      }

      .action{
        padding-top: 15px;

        a{
          text-decoration: none;
          color: $color-1;
          font-size: 16px;
          letter-spacing: 1.5px;
          text-transform: uppercase;
        }
      }
    }
  }
}

</style>