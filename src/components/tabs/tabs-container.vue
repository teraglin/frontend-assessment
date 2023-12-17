<template>
  <div id="tabs-container">
    <tab-component
      v-for="(tab, index) in tabs"
      :key="index"
      :title="tab.title"
      :content="tab.content"
      :image="getImage"
      :index="index"
      :showContent="index === selectedTab"
      @new-selected-tab="updateSelectedTab"
    ></tab-component>
  </div>
</template>

<script>
import TabComponent from "./tab-component.vue";
export default {
  name: "TabsContainer",
  components: {
    TabComponent,
  },
  props: {
    tabs: Array,
    defaultImage: String,
    index: Number,
  },
  data() {
    return {
      selectedTab: 0,
    };
  },
  methods: {
    updateSelectedTab(index) {
      // return console.log(index);
      return (this.selectedTab = index);
    },
    handleShowContent(index) {
      return index === this.slectedTab;
    },
  },
  computed: {
    getImage() {
      return this.tabs.image ? this.tabs.image : this.defaultImage;
    },
    showContent(index) {
      return this.handleShowContent(index);
    },
  },
};
</script>

<style>
#tabs-container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
  align-items: flex-start;
  gap: 50px;
  padding: 50px;
}
</style>
