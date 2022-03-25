<template>
  <div class="container-fluid sfondo">
    <div class="caricamento" v-if="arrayAlbum == null">
      <h1>Dati in fase di caricamento...</h1>
    </div>
    <div v-else class="container">
      <div class="row gap-3 justify-content-center padding">
        <carta-disco
          v-for="disco in funzioneCambioGenere()"
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

  props: {
    genereSelezionato: String,
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

  methods: {
    funzioneCambioGenere(response) {
      if (this.genereSelezionato == "general") {
        this.arrayAlbum = response.data.response;
      } else if (this.genereSelezionato == "rock") {
        this.arrayAlbum = response.data.response.filter((Element) => {
          return Element.genre == "Rock";
        });
      } else if (this.genereSelezionato == "pop") {
        this.arrayAlbum = response.data.response.filter((Element) => {
          return Element.genre == "Pop";
        });
      } else if (this.genereSelezionato == "metal") {
        this.arrayAlbum = response.data.response.filter((Element) => {
          return Element.genre == "Metal";
        });
      } else {
        this.arrayAlbum = response.data.response.filter((Element) => {
          return Element.genre == "Jazz";
        });
      }
    },
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
