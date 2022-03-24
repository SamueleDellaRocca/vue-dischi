<template>
  <div
    class="col-5 col-sm-4 col-md-3 col-lg-2 text-center padding_card sfondo_color"
  >
    <div class="immagine">
      <img class="img" :src="img" :alt="titolo" />
    </div>
    <h2 class="titolo text-white">{{ titolo }}</h2>
    <div class="grigio">{{ autore }}</div>
    <div class="grigio">{{ anno }}</div>
  </div>
</template>

<script>
export default {
  name: "CartaDisco",
  props: {
    img: String,
    titolo: String,
    autore: String,
    anno: String,
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

.padding_card {
  padding: 2rem 1rem;
}
</style>
