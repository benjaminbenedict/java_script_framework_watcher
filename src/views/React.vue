<template>
  <div class="React">
    <h1>test</h1>
    <p>{{ forks }}</p>
    <!-- <div v-for="photo in photos"> -->
    <!-- <h2>{{ photo.name }}</h2>
      <img v-bind:src="photo.url" v-bind:alt="photo.name" />
      <p>Width: {{ photo.width }}</p>
      <p>Height: {{ photo.height }}</p>
    </div> -->
  </div>
</template>

<style></style>

<script>
import axios from "axios";
export default {
  data: function () {
    return {
      forks: [],
    };
  },
  created: function () {
    this.indexPhotos();
  },
  methods: {
    indexPhotos: function () {
      axios.get("/facebook/react").then((response) => {
        console.log("react", response);
        this.forks = response.data["forks"];
        console.log(response.data["forks"]);
      });
    },
  },
};
</script>
