<template>
  <hero-title
    title="Hello Developer"
    subtitle="Lorem ipsum dolor sit amet, consectetur adipiscing elit"
    :mobileImage="mobileHeroImage"
    :desktopImage="desktopHeroImage"
  ></hero-title>
  <tabs-container :tabs="tabsData" :image="tabImage"></tabs-container>
</template>
<!-- TODO: add mobile image -->

<script>
import HeroTitle from "./components/hero-title.vue";
import TabsContainer from "./components/tabs/tabs-container.vue";

export default {
  name: "App",
  components: {
    HeroTitle,
    TabsContainer,
  },
  data() {
    return {
      tabsDataFile: "data.json",
      mobileHeroImageFile: "1920x650.png",
      desktopHeroImageFile: "600x600.png",
      tabImageFile: "400x300.png",
    };
  },
  methods: {
    getImage(image) {
      // return console.log("a", image);
      return require("@/assets/" + image);
    },
    getData(data) {
      // return console.log("aa", data);
      return require("@/data/" + data);
    },
  },
  computed: {
    mobileHeroImage() {
      return this.getImage(this.mobileHeroImageFile);
    },
    desktopHeroImage() {
      return this.getImage(this.desktopHeroImageFile);
    },
    tabImage() {
      return this.getImage(this.tabImageFile);
    },
    tabsData() {
      return this.getData(this.tabsDataFile);
    },
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
  color: #000;
  margin: 0;
}
</style>
