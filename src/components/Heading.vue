<template>
  <div class="heading">
    <!--Desktop view-->
    <div class="container">
      <div class="itemleft order-2" order="2">
        <h1 style="padding-bottom:0; margin-bottom:0">Christopher Kühtz</h1>
        <h4 style="padding-top:0; margin-top:0">Frontend Developer</h4>
        <h3>Nunnenbeckstraße 32</h3>
        <h3>90489 Nürnberg</h3>
        <h3>+4915172109146</h3>
        <h3>chriskuehtz@gmail.com</h3>
      </div>
      <div :class="breakpoints.sm ? 'itemleft order-1' : 'itemright order-3'">
        <img
          :class="breakpoints.sm ? 'profileMobile' : 'profile'"
          src="../assets/profile.png"
          alt="Thats supposed to be me"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "heading",
  components: {},
  props: { breakpoints: Array },
  data() {
    return {
      h: window.innerHeight,
      w: window.innerWidth,
    };
  },
};
</script>

<style>
.heading {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  padding-bottom: 1rem;
  color: #2c3e50;
  margin-top: 4rem;
}
.profile {
  height: 20vw;
  width: 20vw;
}
.profileMobile {
  height: 100%;
  width: 100%;
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
.order-1 {
  order: 1;
}
.order-2 {
  order: 2;
}
.order-3 {
  order: 3;
}
</style>
