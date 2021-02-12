<template>
  <div class="heading">
    <!--Desktop view-->
    <div class="container">
      <div class="itemleft order-2" order="2">
        <h1 style="padding-bottom:0; margin-bottom:0">{{ data.name }}</h1>
        <h4 class="subline">{{ data.tagline }}</h4>
        <h3>{{ data.adress }}</h3>
        <h3>{{ data.city }}</h3>
        <h3>{{ data.mobile }}</h3>
        <h3>{{ data.email }}</h3>
      </div>
      <div :class="breakpoints.sm ? 'itemleft order-1' : 'itemright order-3'">
        <img
          :class="
            breakpoints.sm
              ? breakpoints.xs
                ? 'profileMobile profileXS'
                : 'profileMobile'
              : 'profile'
          "
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
  props: { data: Object, breakpoints: Object },
  data() {
    return {
      h: window.innerHeight,
      w: window.innerWidth,
    };
  },
};
</script>

<style>
h3 {
  margin-bottom: 0.5rem;
  margin-top: 0.5rem;
}
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
  width: 100%;
}
.profileXS {
  width: 90%;
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
