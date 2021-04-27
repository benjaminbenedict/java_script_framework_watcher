<template>
  <div class="React">
    <h1>test</h1>
    <p>{{ ReactForks }}</p>
    <p>{{ ReactStargazers }}</p>
    <p>{{ ReactWatchers }}</p>
    <p>{{ VueForks }}</p>
    <p>{{ VueStargazers }}</p>
    <p>{{ VueWatchers }}</p>
    <p>{{ AngularForks }}</p>
    <p>{{ AngularStargazers }}</p>
    <p>{{ AngularWatchers }}</p>
    <p>{{ EmberForks }}</p>
    <p>{{ EmberStargazers }}</p>
    <p>{{ EmberWatchers }}</p>
    <p>{{ SvElteForks }}</p>
    <p>{{ SvElteStargazers }}</p>
    <p>{{ SvElteWatchers }}</p>
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
      ReactForks: null,
      ReactStargazers: null,
      ReactWatchers: null,
      VueForks: null,
      VueStargazers: null,
      VueWatchers: null,
      AngularForks: null,
      AngularStargazers: null,
      AngularWatchers: null,
      EmberForks: null,
      EmberStargazers: null,
      EmberWatchers: null,
      SvElteForks: null,
      SvElteStargazers: null,
      SvElteWatchers: null,
    };
  },
  created: function () {
    this.indexReact();
    this.indexVue();
    this.indexAngular();
    this.indexEmber();
    this.indexSvElete();
  },
  methods: {
    indexReact: function () {
      axios.get("/facebook/react").then((response) => {
        console.log("react", response);
        this.ReactForks = response.data["forks"];
        this.ReactStargazers = response.data["stargazers_count"];
        this.ReactWatchers = response.data["subscribers_count"];
      });
    },
    indexAngular: function () {
      axios.get("/angular/angular").then((response) => {
        console.log("angular", response);
        this.AngularForks = response.data["forks"];
        this.AngularStargazers = response.data["stargazers_count"];
        this.AngularWatchers = response.data["subscribers_count"];
      });
    },
    indexVue: function () {
      axios.get("/vuejs/vue").then((response) => {
        console.log("vue", response);
        this.VueForks = response.data["forks"];
        this.VueStargazers = response.data["stargazers_count"];
        this.VueWatchers = response.data["subscribers_count"];
      });
    },
    indexEmber: function () {
      axios.get("/emberjs/ember.js").then((response) => {
        console.log("Ember", response);
        this.EmberForks = response.data["forks"];
        this.EmberStargazers = response.data["stargazers_count"];
        this.EmberWatchers = response.data["subscribers_count"];
      });
    },
    indexSvElete: function () {
      axios.get("/sveltejs/svelte").then((response) => {
        console.log("SvElete", response);
        this.SvElteForks = response.data["forks"];
        this.SvElteStargazers = response.data["stargazers_count"];
        this.SvElteWatchers = response.data["subscribers_count"];
      });
    },
  },
};
</script>
