<template>
  <div class="container">
    <h1 class="title">Albums de prueba</h1>
    <div class="columns is-multiline">
      <AlbumCard :album="album" v-for="album in albums" :key="album.id"></AlbumCard>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import env from "../config/env"; //importar end point
import AlbumCard from "../components/AlbumCard";
export default {
  name: "indexPage",
  components: {
    AlbumCard
  },
  data() {
    return {
      albums: []
    };
  },
  //hacer consulta cuando el componente es creado
  created() {
    // //async await

    // let response = axios.get(`${env.endpoint}/albums`)
    // this.albums = response.data;

    //promesa
    axios.get(`${env.endpoint}/albums`).then(response => {
      this.albums = response.data;
    });
  }
};
</script>

<style scoped></style>
