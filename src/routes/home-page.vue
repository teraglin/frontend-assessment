<template>
  <div id="home">
    <a class="home__link" href="#/exercise-1">Exercise 1</a>
    <a class="home__link" href="#/exercise-2">Exercise 2</a>
  </div>
</template>

<script>
export default {
  name: "HomePage"
};
</script>

<style>
#home {
  display: flex;
  height: calc(100vh - 50px);
  width: 100%;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 50px;
}

.home__link {
  height: 50px;
  background: var(--palette-primary);
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 16px;
  padding: 10px;
  color: var(--palette-white);
  text-decoration: none;
  border-radius: 10px;
  cursor: pointer;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
  &:hover {
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.4);
  }
  &:active {
    box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.4);
  }
}
</style>
