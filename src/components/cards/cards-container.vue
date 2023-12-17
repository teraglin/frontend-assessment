<template>
  <div id="cards-container">
    <card-component
      v-for="(card, index) in cards"
      :key="index"
      :content="card.content"
      :image="getImage"
      :index="index"
      :showContent="index === selectedCard"
      @new-selected-card="updateSelectedCard"
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
    defaultImage: String,
    index: Number
  },
  data() {
    return {
      selectedCard: 0
    };
  },
  methods: {
    updateSelectedCard(index) {
      return (this.selectedCard = index);
    },
    handleShowContent(index) {
      return index === this.selectedCard;
    }
  },
  computed: {
    getImage() {
      return this.cards.image ? this.cards.image : this.defaultImage;
    },
    showContent(index) {
      return this.handleShowContent(index);
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
