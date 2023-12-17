<template>
  <a id="tab-button" :target="target" rel="noopener noreferrer" :href="href">
    <slot></slot>
  </a>
</template>

<script>
export default {
  name: "TabButton",
  props: {
    target: String,
    href: String,
  },
  methods: {},
};
</script>

<style>
#tab-button {
  padding: 10px 20px;
  border: 3px solid var(--palette-black);
  background: var(--palette-white);
  border-radius: 50px;
  text-transform: uppercase;
  font-weight: bold;
  text-align: center;
}
</style>
