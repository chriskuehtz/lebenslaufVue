<template>
  <div id="heading">
    <!--Desktop view-->
    <div v-if="h < w">
      <div class="container">
        <div class="itemleft">
          <h1 style="padding-bottom:0; margin-bottom:0">Christopher Kühtz</h1>
          <h4 style="padding-top:0; margin-top:0">Frontend Developer</h4>
          <h2>Nunnenbeckstraße 32</h2>
          <h2>90489 Nürnberg</h2>
          <h2>+4915172109146</h2>
          <h2>chriskuehtz@gmail.com</h2>
        </div>
        <div class="itemright">
          <img
            src="../assets/profile.png"
            alt="Thats supposed to be me"
            id="profile"
          />
        </div>
      </div>
    </div>
    <!--Mobile view-->
    <div v-else>
      <div class="container">
        <div class="itemleft">
          <img
            src="../assets/profile.png"
            alt="Thats supposed to be me"
            id="profileMobile"
          />
        </div>
        <div class="itemleft">
          
          <h1 style="padding-bottom:0; margin-bottom:0">Christopher Kühtz</h1>
          <h4 style="padding-top:0; margin-top:0">Frontend Developer</h4>
          <h3>Nunnenbeckstraße 32</h3>
          <h3>90489 Nürnberg</h3>
          <h3>+4915172109146</h3>
          <h3>chriskuehtz@gmail.com</h3>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "heading",
  components: {},
  data() {
    return {
      h: window.innerHeight,
      w: window.innerWidth,
    };
  },
};
</script>

<style>
#heading {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  padding-left: 5%;
  padding-right: 5%;
  padding-bottom:2%;
  color: #2c3e50;
  margin-top: 60px;
}
#profile {
  height: 20vw;
  width: 20vw;
}
#profileMobile {
  height: 80vw;
  width: 80vw;
}
.container {
  display: flex; /* or inline-flex */
  flex-wrap: wrap;
  justify-content: space-between;
}
.itemleft {
  text-align: left;
}
.itemright {
  text-align: right;
}
</style>
