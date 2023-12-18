<script setup>
import { ref, computed } from "vue";
import HomePage from "./routes/home-page.vue";
import ExerciseOne from "./routes/exercise-1.vue";
import ExerciseTwo from "./routes/exercise-2.vue";
import NotFound from "./routes/404-page.vue";
import NavBar from "./components/navigation/nav-bar.vue";

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
  currentPath.value = window.location.hash;
});

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || "/"].component || NotFound;
});
</script>

<template>
  <nav-bar :routes="routes"></nav-bar>
  <component :is="currentView" />
</template>

<style>
:root {
  /** Pallete */
  --palette-black: #000;
  --palette-white: #fff;
  --palette-primary: #3c557c;
  --palette-secondary: #eeaf61;
  --palette-tertiary: #00c5ff;
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
</style>
