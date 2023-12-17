<template>
  <div id="tab" v-on:click="handleTabClick">
    <img class="tab__image" :src="image" />
    <div class="tab__content" v-html="content" v-show="showContent"></div>
    <tab-button :href="href">Read more</tab-button>
  </div>
</template>

<script>
import TabButton from "../buttons/tab-button.vue";
export default {
  name: "TabComponent",
  components: {
    TabButton,
  },
  props: {
    title: String,
    content: String,
    image: String,
    href: String,
    index: Number,
    showContent: Boolean,
  },
  methods: {
    handleTabClick() {
      this.$emit("new-selected-tab", this.index);
    },
  },
  computed: {},
};
</script>

<style>
#tab {
  border-radius: 10px;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
  padding: 20px;
  max-width: 400px;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  gap: 20px;
  cursor: pointer;
  &:hover {
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.4);
    transition: box-shadow 0.2s ease-in-out;
  }
  &:active {
    box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.2);
    transition: box-shadow 0s linear;
  }
}
.tab__image {
  width: 100%;
  max-width: 400px;
}
.tab__content > * {
  margin: 0;
}
.tab__content > p {
  text-align: center;
}
</style>
