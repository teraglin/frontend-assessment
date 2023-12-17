<template>
  <li
    class="tabs__list__section"
    v-on:click="handleTabClick"
    :selected="selectedTab === index"
  >
    {{ title }}
  </li>
</template>

<script>
export default {
  name: "TabSection",
  props: {
    title: String,
    index: Number,
    selectedTab: Number
  },
  methods: {
    handleTabClick() {
      this.$emit("new-selected-tab", this.index);
    }
  }
};
</script>

<style>
.tabs__list__section {
  padding: 0px 10px;
  background: var(--palette-black);
  color: var(--palette-white);
  transition: background 0.2s linear;
  &[selected="true"] {
    background: var(--palette-white);
    color: var(--palette-black);
  }
}
</style>
