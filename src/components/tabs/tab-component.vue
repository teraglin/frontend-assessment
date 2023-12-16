<template>
  <div id="tab">
    <img class="tab__image" :src="image" />
    <div class="tab__content" v-html="content"></div>
    <button class="tab__button">Read More</button>
  </div>
</template>

<script>
export default {
  name: "TabComponent",
  props: {
    title: String,
    content: String,
    image: String,
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
}
.tab__image {
  background: grey;
  width: 100%;
  max-width: 400px;
}
.tab__content > p {
  text-align: center;
}
</style>
