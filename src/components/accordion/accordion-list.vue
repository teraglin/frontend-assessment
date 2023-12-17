<template>
  <ul id="accordion">
    <accordion-section
      v-for="(tab, index) in tabs"
      :title="tab.title"
      :content="tab.content"
      :index="index"
      :selected-tab="selectedTab"
      :key="index"
      @new-selected-tab="emitSelectedTab"
    ></accordion-section>
  </ul>
</template>

<script>
import AccordionSection from "./accordion-section.vue";
export default {
  name: "AccordionList",
  components: {
    AccordionSection
  },
  props: {
    tabs: Array,
    selectedTab: Number
  },
  methods: {
    emitSelectedTab(index) {
      this.$emit("new-selected-tab", index);
    }
  }
};
</script>

<style>
#accordion {
  list-style-type: none;
  padding: 0;
  margin: 0;
  width: 100%;
}
</style>
