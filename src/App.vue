<template>
  <hero-title
    title="Hello Developer!"
    subtitle="Lorem ipsum dolor sit amet, consectetur adipiscing elit"
  ></hero-title>
  <tabs-container></tabs-container>
</template>

<script>
import HeroTitle from "./components/hero-title.vue";
import TabsContainer from "./components/tabs/tabs-container.vue";

export default {
  name: "App",
  components: {
    HeroTitle,
    TabsContainer,
  },
};
</script>

<style>
body {
  margin: 0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0;
}
</style>
