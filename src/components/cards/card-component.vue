<template>
  <div id="card" v-on:click="handleCardClick">
    <img class="card__image" :src="image" />
    <div class="card__content" v-html="content" v-show="showContent"></div>
    <card-button :href="href">Read more</card-button>
  </div>
</template>

<script>
import CardButton from "../buttons/card-button.vue";
export default {
  name: "CardComponent",
  components: {
    CardButton
  },
  props: {
    title: String,
    content: String,
    image: String,
    href: String,
    index: Number,
    showContent: Boolean
  },
  methods: {
    handleCardClick() {
      this.$emit("new-selected-card", this.index);
    }
  },
  computed: {}
};
</script>

<style>
#card {
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
  transition: box-shadow 0.2s ease-in-out;
  &:hover {
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.4);
  }
  &:active {
    box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.2);
    transition: box-shadow 0s linear;
  }
}
.card__image {
  width: 100%;
  max-width: 400px;
}
.card__content > * {
  margin: 0;
}
.card__content > p {
  text-align: center;
}
</style>
