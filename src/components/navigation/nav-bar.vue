<template>
  <nav id="nav-bar">
    <ul class="nav-bar__list">
      <li
        class="nav-bar__list-item"
        v-for="(route, index) in routes"
        :key="index"
      >
        <a :href="route.href">
          {{ route.name }}
        </a>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "NavBar",
  props: {
    routes: Object
  }
};
</script>

<style>
#nav-bar {
  width: 100vw;
  background: var(--palette-secondary);
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}

.nav-bar__list {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  list-style: none;
  gap: 30px;
}

.nav-bar__list-item > a {
  color: var(--palette-black);
  font-weight: bold;
  text-decoration: none;
}
</style>
