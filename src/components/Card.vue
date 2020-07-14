<template>
  <div class="card">
    <h1 @click="setCollapsed()">
      {{ data.name }}
      <span class="dropButton" v-if="collapsed === true">
        <i class="fas fa-caret-down"></i>
      </span>
      <span class="dropButton" v-else> <i class="fas fa-caret-up"></i> </span>
    </h1>
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
</style>
