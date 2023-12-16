<template>
  <div id="tab-component">
    <div class="image"></div>
    <div v-html="content"></div>
    <button>Read More</button>
  </div>
</template>

<script>
export default {
  name: "TabComponent",
  props: {
    title: String,
    content: String,
  },
};
</script>

<style>
#tab-component {
  border: 1px solid black;
  padding: 10px;
  min-width: 400px;
  max-width: 400px;
}
.image {
  background: grey;
  min-width: 400px;
  max-width: 400px;
  min-height: 300px;
  max-height: 300px;
}
</style>
