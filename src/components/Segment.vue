<template>
  <div class="segment">
    <div class="titlebox" @click="setCollapsed()">
      <h1 class="title" :class="collapsed ? '' : 'accent'">
        {{
          breakpoints.sm && data.hasOwnProperty("titleSmall")
            ? data.titleSmall
            : data.title
        }}
      </h1>
      <i
        class="caret"
        :class="collapsed ? 'fas fa-caret-down' : 'fas fa-caret-up accent'"
      ></i>
    </div>
    <div v-if="collapsed === false">
      <div class="container">
        <input
          v-if="data.hasOwnProperty('searchbar')"
          class="searchbar"
          type="text"
          placeholder="Suche einen Skill"
          v-model="search"
        />
      </div>

      <div v-if="search === ''">
        <div class="container">
          <div v-for="l in data.list" :key="l">
            <div class="item">
              <Card :data="l" :breakpoints="breakpoints" />
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
            :key="l[1]"
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
    breakpoints: Object,
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
  background-color: var(--my-bg-color);
  color: var(--my-color);
  border-color: var(--my-accent-color);
  border-radius: 0.5rem;
  border-style: solid;
  border-width: 1px;
  margin: 0.5rem;
  margin-left: 0;
  max-width: 480px !important;
  overflow: hidden;
}
::placeholder {
  color: var(--my-color);
  opacity: 1;
}
.titlebox {
  display: flex; /* or inline-flex */
  flex-wrap: wrap;
  justify-content: space-between;
  width: 100%;
  border-top: 1px solid var(--my-color);
}
.title {
  width: 90%;
}
.caret {
  margin: auto;
  font-size: 2.5rem;
  width: 10%;
}
.container {
  display: grid;
  align-content: stretch;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
}

.card {
  border: 1px solid var(--my-accent-color);
  border-radius: 5px;
  padding: 0.5rem;
  margin: 0.5rem;
  margin-left: 0;
}
</style>
