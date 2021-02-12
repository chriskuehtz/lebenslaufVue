<template>
  <div class="heading">
    <!--Desktop view-->
    <div class="container">
      <div class="itemleft order-2" order="2">
        <h1 style="padding-bottom:0; margin-bottom:0">Christopher Kühtz</h1>
        <h4 class="subline">Frontend Developer</h4>
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
  padding-bottom: 1rem;
  margin-top: 4rem;
}
.subline {
  padding-top: 0;
  margin-top: 0;
  color: var(--my-accent-color);
}
.profile {
  border: solid 0.25rem var(--my-accent-color);
  border-radius: 50%;
  height: 20vw;
  width: 20vw;
}
.profileMobile {
  box-sizing: border-box;
  border: solid 0.25rem var(--my-accent-color);
  border-radius: 50%;
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
</style>
