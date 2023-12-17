<template>
  <div id="tab">
    <img class="tab__image" :src="image" />
    <div class="tab__content" v-html="content"></div>
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
  },
};
</script>

<style>
#tab {
  border-radius: 10px;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
  padding: 20px;
  min-width: 400px;
  max-width: 400px;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
}
.tab__image {
  width: 100%;
  max-width: 400px;
}
.tab__content > p {
  text-align: center;
}
</style>
