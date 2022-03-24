<template>
  <div class="col-5 col-sm-4 col-md-3 col-lg-2 text-center p_card sfondo_color">
    <div class="immagine">
      <img class="img" :src="albumData.poster" :alt="albumData.title" />
    </div>
    <h2 class="titolo text-white">{{ albumData.title }}</h2>
    <div class="grigio">{{ albumData.author }}</div>
    <div class="grigio">{{ albumData.year }}</div>
  </div>
</template>

<script>
export default {
  name: "CartaDisco",
  props: {
    albumData: Object,
  },
};
</script>

<style scoped lang="scss">
.img {
  width: 100%;
}

.grigio {
  color: gray;
}

.sfondo_color {
  background-color: hsl(210deg 21% 23%);
}

.p_card {
  padding: 2rem 1rem;
}
</style>
