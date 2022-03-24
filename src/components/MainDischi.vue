<template>
  <div class="container">
    <div class="row">
      <div class="text-center bg-primary">ciao</div>
    </div>
    <carta-disco></carta-disco>
  </div>
</template>

<script>
import CartaDisco from "./CartaDisco.vue";

export default {
  name: "MainDischi",
  components: {
    CartaDisco,
  },
};
</script>

<style scoped lang="scss"></style>
