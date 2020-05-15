<template>
  <h1>hola mundo</h1>
</template>

<script>
//las rutas de nuxt se definen por estructuras de carpetas
export default {
  name: "AlbumSinglePage",
  created() {
    let albumId = this.$route.params.id;
    console.log(albumId);
  },
};
</script>

<style></style>
