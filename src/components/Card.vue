<template>
  <div class="card">
    <div class="titlebox no-border" @click="setCollapsed()">
      <h1 class="title w100 center">
        {{ data.name }}
      </h1>
      <i
        class="caret w100 center"
        :class="collapsed ? 'fas fa-caret-down' : 'fas fa-caret-up'"
      ></i>
    </div>
    <div v-if="collapsed === false">
      <div v-if="data.hasOwnProperty('daterange')">
        <p>{{ data.daterange }}</p>
      </div>
      <p>{{ data.text }}</p>
      <div v-if="data.hasOwnProperty('skills')">
        <SkillBox :data="data.skills" />
      </div>
      <div v-if="data.hasOwnProperty('links')">
        <LinkBox :data="data.links" />
      </div>
    </div>
    <div v-else></div>
  </div>
</template>

<script>
import LinkBox from "./LinkBox.vue";
import SkillBox from "./SkillBox.vue";
export default {
  name: "card",
  components: { LinkBox, SkillBox },
  props: {
    data: Object,
    breakpoints: Array,
  },
  data() {
    return { collapsed: true };
  },
  methods: {
    setCollapsed() {
      this.collapsed = !this.collapsed;
    },
  },
};
</script>

<style>
.card {
  border: 1px solid #2c3e50;
  border-radius: 5px;
  padding: 0.5em;

  margin: 0.5em;
  margin-left: 0;
}
.w100 {
  width: 100% !important;
}
.center {
  text-align: center;
}
.no-border {
  border: none !important;
}
</style>
