<template>
  <a
    id="card-button"
    :target="target"
    rel="noopener noreferrer"
    :href="checkHref"
  >
    <slot></slot>
  </a>
</template>

<script>
export default {
  name: "CardButton",
  props: {
    target: String,
    href: String
  },
  methods: {},
  computed: {
    checkHref() {
      return this.href ? this.href : "#";
    }
  }
};
</script>

<style>
#card-button {
  padding: 10px 20px;
  border: 3px solid var(--palette-black);
  background: var(--palette-white);
  border-radius: 50px;
  text-transform: uppercase;
  font-weight: bold;
  text-align: center;
  text-decoration: none;
  color: var(--palette-black);
}
</style>
