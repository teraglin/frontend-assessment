<script setup>
import { ref, computed } from "vue";
import HomePage from "./routes/home-page.vue";
import ExerciseOne from "./routes/exercise-1.vue";
import ExerciseTwo from "./routes/exercise-2.vue";
import NotFound from "./routes/404-page.vue";

const routes = {
  "/": {
    component: HomePage,
    href: "#/",
    name: "Home"
  },
  "/exercise-1": {
    component: ExerciseOne,
    href: "#/exercise-1",
    name: "Exercise 1"
  },
  "/exercise-2": {
    component: ExerciseTwo,
    href: "#/exercise-2",
    name: "Exercise 2"
  }
};

const currentPath = ref(window.location.hash);

window.addEventListener("hashchange", () => {
  console.log(window.location.hash);
  currentPath.value = window.location.hash;
});

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || "/"].component || NotFound;
});
</script>

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
  <component :is="currentView" />
</template>

<style>
:root {
  /** Pallete */
  --palette-black: #000;
  --palette-white: #fff;
}

* {
  box-sizing: border-box;
}

body {
  margin: 0;
}

#app {
  font-family: Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: var(--palette-black);
  margin: 0;
}

#nav-bar {
  width: 100vw;
  background: var(--palette-black);
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
  color: var(--palette-white);
  text-decoration: none;
}
</style>
