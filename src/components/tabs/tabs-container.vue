<template>
  <div id="tabs-container">
    <tab-component
      v-for="(tab, index) in tabs"
      :key="index"
      :title="tab.title"
      :content="tab.content"
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
  },
};
</script>

<style>
#tabs-container {
  border: 1px solid cyan;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  gap: 10px;
}
</style>
