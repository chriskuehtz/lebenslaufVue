<template>
  <div class="segment">
    <div class="titlebox" @click="setCollapsed()">
      <h1 class="title">
        {{
          breakpoints.sm && data.hasOwnProperty("titleSmall")
            ? data.titleSmall
            : data.title
        }}
      </h1>
      <i
        class="caret"
        :class="collapsed ? 'fas fa-caret-down' : 'fas fa-caret-up'"
      ></i>
    </div>
    <div v-if="collapsed === false">
      <input
        v-if="data.hasOwnProperty('searchbar')"
        class="searchbar"
        type="text"
        placeholder="Suche einen Skill"
        v-model="search"
      />

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
              <Card :data="l" :breakpoints="breakpoints" />
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
    breakpoints: Array,
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
.searchbar {
  font-size: 2rem;
  color: black;
  border-radius: 0.5rem;
  border-style: solid;
  border-width: 1px;
  margin-bottom: 0.5rem;
  width: clamp(40vw, 90%, 480px);
  overflow: hidden;
}
.titlebox {
  display: flex; /* or inline-flex */
  flex-wrap: wrap;
  justify-content: space-between;
  width: 100%;
  border-top: 1px solid #2c3e50;
}
.title {
  width: 80%;
}
.caret {
  margin: auto;
  font-size: 2.5rem;
  width: 20%;
  height: 20%;
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
