<template>
  <div class="container-fluid sfondo">
    <div class="caricamento" v-if="arrayAlbum == null">
      <h1>Dati in fase di caricamento...</h1>
    </div>
    <div v-else class="container">
      <div class="row gap-3 justify-content-center padding">
        <carta-disco
          v-for="disco in arrayAlbum"
          :key="disco.title"
          :album-data="disco"
        ></carta-disco>
      </div>
    </div>
  </div>
</template>

<script>
import CartaDisco from "./CartaDisco.vue";
import axios from "axios";

export default {
  name: "MainDischi",

  data() {
    return {
      arrayAlbum: null,
    };
  },

  components: {
    CartaDisco,
  },

  created() {
    setTimeout(() => {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((response) => {
          console.log(response);
          this.arrayAlbum = response.data.response;
        });
    }, 3000);
  },
};
</script>

<style scoped lang="scss">
.sfondo {
  background-color: hsl(209deg 33% 17%);
}

.padding {
  padding: 3rem 0px;
}

.caricamento {
  width: 100%;
  height: calc(100vh - 100px);
  display: flex;

  h1 {
    margin: auto;
    font-size: 3rem;
    color: white;
  }
}
</style>
