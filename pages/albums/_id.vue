<template>
  <div class="container">
    <header>
      <nuxt-link to="/">Regresar</nuxt-link>
    </header>
    <h1 class="title">{{ album.title }}</h1>

    <div class="columns is-multiline">
      <div class="column is-one-quarter" v-for="photo in photos" :key="photo.id">
        <img :src="photo.url" :alt="photo.title" />
      </div>
    </div>
  </div>
</template>

<script>
//las rutas de nuxt se definen por estructuras de carpetas

import axios from "axios";
import env from "../../config/env"; //importar end point
import router from "vue-router";
export default {
  name: "AlbumSinglePage",
  data() {
    return {
      album: {},
      photos: []
    };
  },
  async created() {
    //async await

    let albumResponse = await axios.get(
      `${env.endpoint}/albums/${this.$route.params.id}`
    );
    this.album = albumResponse.data;

    // //promesa
    // axios
    //   .get(`${env.endpoint}/albums/${this.$route.params.id}`)
    //   .then(albumResponse => {
    //     this.album = albumResponse.data;
    //   });

    //async await

    let photoResponse = await axios.get(
      `${env.endpoint}/albums/${this.$route.params.id}/photos`
    );
    this.photos = photoResponse.data;

    // //promesa

    // axios
    //   .get(`${env.endpoint}/albums/${this.$route.params.id}/photos`)
    //   .then(photoResponse => {
    //     console.log(photoResponse.data);
    //     this.photos = photoResponse.data;
    //   });
  }
};
</script>

<style>
.container {
  text-align: center;
}

.title {
  margin: 2em;
}
</style>
