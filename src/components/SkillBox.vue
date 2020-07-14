<template>
  <div id="skillbox">
    <h3>Skills:</h3>
    <div class="skillContainer">
      <div v-for="l in data" :key="l.text">
        <div class="skill">
          <p>
            {{ l.text }}
            <i v-if="l.hasOwnProperty('icon')" v-bind:class="l.icon"></i>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "linkbox",
  components: {},
  props: {
    data: Array,
  },
};
</script>

<style>
#segment {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  padding-left: 5%;
  padding-right: 5%;
  color: #2c3e50;
}

.skillContainer {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(27%, 1fr));
}

.skill {
  padding-right: 0.5em;
  min-width: 50%;
}
</style>
