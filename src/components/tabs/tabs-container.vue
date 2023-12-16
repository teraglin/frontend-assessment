<template>
  <div id="tabs-container">
    <tab-component
      v-for="(tab, index) in tabs"
      :key="index"
      :title="tab.title"
      :content="tab.content"
      :image="image"
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
    image: String,
  },
};
</script>

<style>
#tabs-container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  gap: 50px;
  padding: 50px;
}
</style>
