<template>
  <div class="container-fluid sfondo">
    <div class="container">
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
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        console.log(response);
        this.arrayAlbum = response.data.response;
      });
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
</style>
