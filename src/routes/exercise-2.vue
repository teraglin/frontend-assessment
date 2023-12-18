<template>
  <div class="exercise2">
    <accordion-list
      className="tabs-display--mobile"
      :tabs="tabs"
      :selected-tab="selectedTab"
      @new-selected-tab="updateSelectedTab"
    ></accordion-list>
    <tab-list
      className="tabs-display--desktop"
      :tabs="tabs"
      :selected-tab="selectedTab"
      @new-selected-tab="updateSelectedTab"
    ></tab-list>
  </div>
</template>

<script>
import AccordionList from "../components/accordion/accordion-list.vue";
import TabList from "../components/tabs/tab-list.vue";

export default {
  name: "ExerciseTwo",
  components: {
    AccordionList,
    TabList
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

<style>
.exercise2 {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 20px 10px;
}
.tabs-display--mobile {
  @media (min-width: 600px) {
    display: none;
  }
}

.tabs-display--desktop {
  display: none;
  @media (min-width: 600px) {
    display: block;
  }
}
</style>
