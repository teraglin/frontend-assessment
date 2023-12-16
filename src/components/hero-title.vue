<template>
  <div id="hero-title">
    <h1 class="title">{{ title }}</h1>
    <p class="subtitle">{{ subtitle }}</p>
  </div>
</template>

<script>
export default {
  name: "HeroTitle",
  props: {
    title: String,
    subtitle: String,
  },
};
</script>

<style>
#hero-title {
  flex-grow: 1;
  color: #fff;
  background: grey;
  max-width: 1920px;
  height: 650px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}
.title {
  margin: 0;
}
.subtitle {
  margin: 0;
}
</style>
