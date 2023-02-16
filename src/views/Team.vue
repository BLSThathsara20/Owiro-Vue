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
  <div class="col">
    <div class="card h-100">
      <img src="../assets/image/team/Team-img-1.jpg" class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
      </div>
    </div>
  </div>
  <div class="col">
    <div class="card h-100">
      <img src="../assets/image/team/Team-img-2.jpg" class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">This is a short card.</p>
      </div>
    </div>
  </div>
  <div class="col">
    <div class="card h-100">
      <img src="../assets/image/team/Team-img-1.jpg" class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content.</p>
      </div>
    </div>
  </div>
  <div class="col">
    <div class="card h-100">
      <img src="../assets/image/team/Team-img-2.jpg" class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
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
  components: {
    
  },
  data() {
    return {
      team: [
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

  //Style Team Members Section
  .members{
    padding-bottom: 100px;
  }
}

</style>