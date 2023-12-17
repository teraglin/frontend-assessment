<template>
  <div id="cards-container">
    <card-component
      v-for="(card, index) in cards"
      :key="index"
      :content="card.content"
      :image="getImage"
    ></card-component>
  </div>
</template>

<script>
import CardComponent from "./card-component.vue";
export default {
  name: "CardsContainer",
  components: {
    CardComponent
  },
  props: {
    cards: Array,
    defaultImage: String
  },
  computed: {
    getImage() {
      return this.cards.image ? this.cards.image : this.defaultImage;
    }
  }
};
</script>

<style>
#cards-container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
  align-items: flex-start;
  gap: 50px;
  padding: 50px;
}
</style>
