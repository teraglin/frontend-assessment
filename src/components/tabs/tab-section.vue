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
      return this.$emit("new-selected-tab", this.index);
    }
  }
};
</script>

<style>
.tabs__list__section {
  position: relative;
  padding: 0px 10px;
  color: var(--palette-white);
  font-size: 24px;
  cursor: pointer;
  z-index: 1;
  overflow: hidden;
  transition: color 0.1s linear;
  &::after {
    position: absolute;
    content: "";
    border-radius: 50px;
    top: 50%;
    left: 50%;
    width: 0px;
    height: 0px;
    background: var(--palette-white);
    z-index: -1;
    transition: width 0.1s linear, height 0.1s linear, top 0.1s linear,
      left 0.1s linear;
  }
  &[selected="true"] {
    color: var(--palette-black);
    &::after {
      top: -25%;
      left: -25%;
      width: 150%;
      height: 150%;
    }
  }
}
</style>
