<template>
  <div class="container-fluid sfondo">
    <div class="row align-items-center altezza">
      <div class="col-10"><h1 class="text-white">Spotify</h1></div>
      <div class="col-2">
        <label class="text-white p-1" for="cars">Generi Musicali:</label>
        <select class="p-1 rounded" name="genere" id="genere">
          <option default value="general">General</option>
          <option value="rock">Rock</option>
          <option value="pop">Pop</option>
          <option value="metal">Metal</option>
          <option value="jazz">Jazz</option>
        </select>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HeaderDischi",
};
</script>

<style scoped lang="scss">
.sfondo {
  background-color: hsl(210deg 21% 23%);
  height: 100px;
}

.altezza {
  height: 100%;
}
</style>
