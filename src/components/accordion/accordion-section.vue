<template>
  <li class="accordion__section">
    <h1 class="accordion__section__title" v-on:click="handleTabClick">
      {{ title }}
    </h1>
    <div
      v-show="index === selectedTab"
      class="accordion__section__content"
      v-html="content"
    ></div>
  </li>
</template>

<script>
export default {
  name: "AccordionSection",
  props: {
    title: String,
    content: String,
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
.accordion__section {
}
.accordion__section__title {
  background: var(--palette-black);
  color: var(--palette-white);
  padding: 0 10px;
  margin: 0;
  cursor: pointer;
}
.accordion__section__content {
  padding: 10px 20px;
  & > ul,
  ol {
    margin-bottom: 10px;
  }
}
</style>
