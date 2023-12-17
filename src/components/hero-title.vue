<template>
  <div id="hero">
    <img class="hero__image hero__image--mobile" :src="mobileImage" />
    <img class="hero__image hero__image--desktop" :src="desktopImage" />
    <div class="hero-content">
      <h1 class="hero__title">{{ title }}</h1>
      <p class="hero__subtitle">{{ subtitle }}</p>
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
    desktopImage: String,
  },
};
</script>

<style>
#hero {
  position: relative;
  max-height: 650px; /* Look at removing this */
}
.hero__image {
  max-width: 1920px;
  width: 100%;
  margin: 0 auto;
}
.hero__image--mobile {
  display: none;
  @media (min-width: 600px) {
    display: block;
  }
}
.hero__image--desktop {
  @media (min-width: 600px) {
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
}
.hero-content__title {
  margin: 0;
}
.hero-content__subtitle {
  margin: 0;
}
</style>
