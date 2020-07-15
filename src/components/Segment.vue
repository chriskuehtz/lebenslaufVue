<template>
  <div id="segment">
    <div class="title">
      <h1 @click="setCollapsed()">
        {{ data.title }}
        <span class="dropButton" v-if="collapsed === true">
          <i class="fas fa-caret-down"></i>
        </span>
        <span class="dropButton" v-else> <i class="fas fa-caret-up"></i> </span>
      </h1>
    </div>
    <div v-if="collapsed === false">
      <div v-if="data.hasOwnProperty('searchbar')">
        <input
          id="searchbar"
          type="text"
          placeholder="Suche nach einem Skill"
          v-model="search"
        />
      </div>

      <div v-if="search === ''">
        <div class="container">
          <div v-for="l in data.list" :key="l">
            <div class="item">
              <Card :data="l" />
            </div>
          </div>
        </div>
      </div>
      <div v-else>
        <div class="container">
          <div
            v-for="l in data.list.filter((l) =>
              l.skills
                .map((s) => s.text.toLowerCase())
                .includes(search.toLowerCase())
            )"
            :key="l"
          >
            <div class="item">
              <Card :data="l" />
            </div>
          </div>
        </div>
      </div>
    </div>
    <div v-else></div>
  </div>
</template>

<script>
import Card from "./Card.vue";

export default {
  name: "segment",
  components: { Card },
  props: {
    data: Object,
  },
  data() {
    return { collapsed: true, search: "" };
  },
  methods: {
    setCollapsed() {
      this.collapsed = !this.collapsed;
    },
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
#searchbar {
  color: #2c3e50;
  font-size: 2em;
  border-radius: 0.5em;
  border-style: solid;
  border-width: 1px;
  margin-bottom: 0.5em;
}
.title {
  width: 100%;
  border-top: 1px solid #2c3e50;
}
.dropButton {
  padding-left: 1em;
}
.container {
  display: grid;
  align-content: stretch;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
}

.card {
  border: 1px solid #2c3e50;
  border-radius: 5px;
  padding: 0.5em;

  margin: 0.5em;
  margin-left: 0;
}
</style>
