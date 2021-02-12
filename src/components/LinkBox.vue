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
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}
.link {
  color: var(--my-accent-color);
  font-size: 1.5rem;
  text-decoration-line: none;
  margin-left: 1rem;
  margin-right: 2rem;
}
</style>
