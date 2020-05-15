<template>
  <div class="column is-one-quarter">
    <div class="box">
      <h3>{{ album.title }}</h3>
      <nuxt-link class="button is-primary" :to="'/albums/'+album.id">Ver mas</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "AlbumCard", //nombre de componente
  props: {
    album: Object
  }
};
</script>

<style>
.box {
  padding: 1rem;
}

h3 {
  min-height: 5rem;
}
</style>
