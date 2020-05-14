<template>
  <div class="column is-one-quarter">
    <div class="box">
      <h3>{{ album.title }}</h3>
      <a class="button is-primary" href="#">Ver mas</a>
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
