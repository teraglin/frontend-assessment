<template>
  <div>
    <accordion-list
      :tabs="tabs"
      :selected-tab="selectedTab"
      @new-selected-tab="updateSelectedTab"
    ></accordion-list>
  </div>
</template>

<script>
import AccordionList from "../components/accordion/accordion-list.vue";

export default {
  name: "ExerciseTwo",
  components: {
    AccordionList
  },
  data() {
    return {
      tabsDataFile: "tabs-data.json",
      selectedTab: 0
    };
  },
  methods: {
    getData(data) {
      return require("@/data/" + data);
    },
    updateSelectedTab(index) {
      // return console.log(index);
      return (this.selectedTab = index);
    }
  },
  computed: {
    tabs() {
      return this.getData(this.tabsDataFile);
    },
    showContent(index) {
      return this.handleShowContent(index);
    }
  }
};
</script>

<style></style>
