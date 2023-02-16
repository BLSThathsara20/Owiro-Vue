<template>
  <div class="team">
    <section class="top">
      <div class="container">
        <h1 class="title">Our Team</h1>
      </div>
    </section>

    <section class="members">
      <div class="container">
        <div class="row row-cols-1 row-cols-md-3 g-4">
          <div class="col"  v-for="(member, index) in team" v-bind:key="index">
            <div class="card h-100 border-0">
              <div class="wrapper">
                <img :src="member.image" class="card-img-top img-fluid" alt="{{ member.name }}">

                <div class="sm" v-if="member.sm && (member.sm.fb || member.sm.twitter || member.sm.linkdin)">
                  <ul>
                    <li v-if="member.sm.fb"><a :href="member.sm.fb">Facebook</a></li>
                    <li v-if="member.sm.twitter"><a :href="member.sm.twitter">Twitter</a></li>
                    <li v-if="member.sm.linkdin"><a :href="member.sm.linkdin">LinkedIn</a></li>
                  </ul>
                </div>
              </div>
              <div class="card-body">
                <h2 class="card-title name">{{ member.name }}</h2>
                <h3 class="card-text position">{{ member.position }}</h3>
              </div>
            </div>
          </div>
      </div>
      </div>
    </section>

  </div>
</template>

<script>

export default {
  name: 'Team',
  data() {
    return {
      team: [
        {
          name: "Leo Dhouan",
          position: "Team Lead",
          image: require('@/assets/image/team/Team-img-2.jpg'),
          sm: {
            fb : "r",
            twitter : "f",
            linkdin: "f",
          }
        },
        {
          name: "Bred Deen",
          position: "Product Manager",
          image: require('@/assets/image/team/Team-img-1.jpg'),
          sm: {
            fb : "",
            twitter : "f",
            linkdin: "",
          }
        },
        {
          name: "Bred Deen",
          position: "Product Manager",
          image: require('@/assets/image/team/Team-img-2.jpg'),
          sm: {
            fb : "",
            twitter : "f",
            linkdin: "",
          }
        },
        {
          name: "Bred Deen",
          position: "Product Manager",
          image: require('@/assets/image/team/Team-img-1.jpg'),
          sm: {
            fb : "",
            twitter : "f",
            linkdin: "",
          }
        },
      ],
    };
  },
}
</script>


<style lang="scss" scoped>
//Variables
$color-1: #000;

$font-1 : 'Syne', sans-serif;
$font-2 : 'Heebo', sans-serif;

.team{
  .top{
    padding-top: 60px;
    padding-bottom: 80px;
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

  //Style Team Members Section
  .members{
    padding-bottom: 100px;

    .card{
      
      &:hover{
        .wrapper{
          .sm{
            background-color: #ffffffea;

            ul{
              li{
                opacity: 1;
              }
            }
          }
        }
      }

      .name{
      font-family: $font-1;
      font-weight: 600;
      color: #000;
      font-size: 30px;
      line-height: 1.16em;
      text-align: center;
    }
    .position{
      font-family: $font-1;
      font-size: 13px;
      text-transform: uppercase;
      letter-spacing: 4px;
      color: #8a8a8a;
      font-weight: 600;
      text-align: center;
    }

    .wrapper{
      position: relative;

      .sm{
        position: absolute;
        top: 0;
        height: 100%;
        width: 100%;

        display: flex;
        align-items: center;
        justify-content: center;
        background-color: transparent;
        transition: all 0.3s;

        ul{
          display: flex;
          gap: 18px;
          flex-wrap: wrap;
          padding: 0;

          li{
            list-style: none;
            opacity: 0;
            transition: all 0.3s;

            a{
              text-decoration: none;
              color: #000;
              font-size: 13px;
              letter-spacing: 3px;
              font-weight: 600;
              text-transform: uppercase;
              font-family: $font-1;
              transition: all 0.3s;

              &:hover{
                background: linear-gradient(-120deg,rgba(92,195,238,.94),rgba(94,94,240,.94) 46%,rgba(202,151,210,.94));
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
}

</style>