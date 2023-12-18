<template>
  <div id="hero">
    <img class="hero__image hero__image--mobile" :src="mobileImage" />
    <img class="hero__image hero__image--desktop" :src="desktopImage" />
    <div class="hero-content">
      <h1 class="hero-content__title">{{ title }}</h1>
      <p class="hero-content__subtitle">{{ subtitle }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "HeroTitle",
  props: {
    title: String,
    subtitle: String,
    mobileImage: String,
    desktopImage: String
  }
};
</script>

<style>
#hero {
  position: relative;
  height: 650px;
  overflow: hidden;
  @media (max-width: 600px) {
    height: 600px;
  }
  &::after {
    position: absolute;
    content: "";
    top: 0;
    left: 0;
    z-index: 2;
    width: 100%;
    max-width: 1920px;
    height: 100%;
    background: rgba(0, 0, 0, 0.4);
  }
}
.hero__image {
  position: relative;
  top: 0;
}
.hero__image--mobile {
  width: 600px;
  display: none;
  margin-left: calc(50vw - (600px / 2));
  @media (max-width: 600px) {
    display: block;
  }
}
.hero__image--desktop {
  width: 1920px;
  margin-left: calc(50vw - (1920px / 2));
  @media (max-width: 600px) {
    display: none;
  }
}
.hero-content {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  color: var(--palette-white);
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  z-index: 3;
}
.hero-content__title {
  margin: 0;
  font-size: 80px;
  text-align: center;
  @media (max-width: 600px) {
    padding-bottom: 10px;
    width: 500px;
  }
}
.hero-content__subtitle {
  text-align: center;
  margin: 0;
  font-size: 36px;
  @media (max-width: 600px) {
    width: 500px;
  }
}

@media (min-width: 1920px) {
  #hero::after {
    left: calc(50vw - (1920px / 2));
  }
}
</style>
