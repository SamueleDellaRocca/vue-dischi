<template>
  <div
    class="col-5 col-sm-4 col-md-3 col-lg-2 text-center padding_card sfondo_color"
  >
    <div class="immagine">
      <img class="img" :src="AlbumData.poster" :alt="AlbumData.title" />
    </div>
    <h2 class="titolo text-white">{{ AlbumData.title }}</h2>
    <div class="grigio">{{ AlbumData.author }}</div>
    <div class="grigio">{{ AlbumData.year }}</div>
  </div>
</template>

<script>
export default {
  name: "CartaDisco",
  props: {
    AlbumData: Object,
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
