<template>
  <li class="accordion__section">
    <h1 class="accordion__section__title" v-on:click="handleTabClick(index)">
      {{ title }}
    </h1>
    <div
      v-show="index === selectedTab"
      class="accordion__section__content"
      v-html="toggle ? content : `<p class='accordion__empty-display'></p>`"
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
  data() {
    return {
      toggle: true
    };
  },
  methods: {
    handleTabClick(index) {
      if (index === this.selectedTab) {
        this.toggle = !this.toggle;
        return;
      }
      this.toggle = true;
      return this.$emit("new-selected-tab", this.index);
    }
  }
};
</script>

<style>
.accordion__section {
}
.accordion__section__title {
  background: var(--palette-primary);
  color: var(--palette-white);
  padding: 0 10px;
  margin: 0;
  cursor: pointer;
}
.accordion__section__content {
  & > * {
    padding: 10px 20px;
  }
  & > ul,
  ol {
    margin-bottom: 10px;
  }
}
.accordion__empty-display {
  display: none;
}
</style>
