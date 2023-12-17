<template>
  <div id="tabs">
    <ul class="tabs__list">
      <tab-section
        v-for="(tab, index) in tabs"
        :title="tab.title"
        :index="index"
        :selected-tab="selectedTab"
        :key="index"
        @new-selected-tab="emitSelectedTab"
      ></tab-section>
    </ul>
    <div class="tabs__content" v-html="tabs[selectedTab].content"></div>
  </div>
</template>

<script>
import TabSection from "./tab-section.vue";

export default {
  name: "TabList",
  components: {
    TabSection
  },
  props: {
    tabs: Array,
    selectedTab: Number
  },
  methods: {
    handleShowContent(index) {
      return index === this.selectedTab;
    },
    emitSelectedTab(index) {
      this.$emit("new-selected-tab", index);
    }
  }
};
</script>

<style>
#tabs {
  width: 100%;
  max-width: 600px;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.4);
  border-radius: 10px;
  overflow: hidden;
}

.tabs__list {
  list-style-type: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 10px;
  background: var(--palette-primary);
}

.tabs__content {
  padding: 0 20px;
}
</style>
