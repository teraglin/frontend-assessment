<template>
  <hero-title
    title="Hello Developer!"
    subtitle="Lorem ipsum dolor sit amet, consectetur adipiscing elit"
    :mobileImage="mobileHeroImage"
    :desktopImage="desktopHeroImage"
  ></hero-title>
  <cards-container
    :cards="cardsData"
    :defaultImage="cardImage"
  ></cards-container>
</template>

<script>
import HeroTitle from "../components/hero-title.vue";
import CardsContainer from "../components/cards/cards-container.vue";

export default {
  name: "ExerciseOne",
  components: {
    HeroTitle,
    CardsContainer
  },
  data() {
    return {
      cardsDataFile: "cards-data.json",
      desktopHeroImageFile: "1920x650.png",
      mobileHeroImageFile: "600x600.png",
      cardImageFile: "400x300.png"
    };
  },
  methods: {
    getImage(image) {
      return require("@/assets/" + image);
    },
    getData(data) {
      return require("@/data/" + data);
    }
  },
  computed: {
    mobileHeroImage() {
      return this.getImage(this.mobileHeroImageFile);
    },
    desktopHeroImage() {
      return this.getImage(this.desktopHeroImageFile);
    },
    cardImage() {
      return this.getImage(this.cardImageFile);
    },
    cardsData() {
      return this.getData(this.cardsDataFile);
    }
  }
};
</script>

<style></style>
