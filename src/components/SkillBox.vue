<template>
  <div>
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
  name: "skillbox",
  components: {},
  props: {
    data: Array,
  },
};
</script>

<style>
.skillContainer {
  display: flex;
  flex-wrap: wrap;
}

.skill {
  padding-right: 1rem;
  padding-left: 1rem;
  font-size: 1.5rem;
  width: clamp(140px, 200px, 100%);
}
</style>
