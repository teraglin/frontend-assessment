<template>
  <div id="tabs">
    <ul class="tabs__list">
      <tab-section
        v-for="(tab, index) in tabs"
        :title="tab.title"
        :index="index"
        :selected-tab="selectedTab"
        :key="index"
        :toggle="toggle"
        @new-selected-tab="emitSelectedTab"
        @set-toggle="updateToggle"
      ></tab-section>
    </ul>
    <div
      class="tabs__content"
      v-html="
        toggle
          ? tabs[selectedTab].content
          : `<p class='tabs__empty-display'></p>`
      "
    ></div>
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
  data() {
    return {
      toggle: true
    };
  },
  methods: {
    emitSelectedTab(index) {
      if (index === this.selectedTab) {
        this.toggle = !this.toggle;
      } else {
        this.toggle = true;
      }
      console.log(this.toggle);
      this.$emit("new-selected-tab", index);
    },
    updateToggle(toggle) {
      console.log(toggle);
      this.toggle = toggle;
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

.tabs__empty-display {
  display: none;
}
</style>
