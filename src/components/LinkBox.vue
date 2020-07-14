<template>
  <div id="linkbox">
    <h3>Links:</h3>
    <div class="linkContainer">
      <div v-for="l in data" :key="l.name">
        <div class="item">
          <p>
            <a class="link" v-bind:href="l.http">{{ l.name }}</a>
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
.linkContainer {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(1px, 1fr));
}

.item {
  padding-right: 0.5em;
}
.link {
  color: #2c3e50;
  text-decoration-line: none;
}
</style>
