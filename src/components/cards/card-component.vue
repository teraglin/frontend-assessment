<template>
  <div id="card">
    <img class="card__image" :src="image" />
    <div class="card__content" v-html="content"></div>
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
    content: String,
    image: String,
    href: String
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
}
.card__image {
  width: 100%;
  max-width: 400px;
}
.card__content > * {
  margin: 0;
  width: 400px;
  height: 260px;
  font-size: 24px;
}
.card__content > p {
  text-align: center;
}
</style>
