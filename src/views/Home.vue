<template>
  <div class="home">
    <h1>{{ message }}</h1>
    vue: <br />
    stargazers = {{ stargazers_vue }} <br />
    subscribers = {{ subscribers_vue }} <br />
    forks = {{ forks_vue }} <br />
    ang: <br />
    stargazers = {{ stargazers_ang }} <br />
    subscribers = {{ subscribers_ang }} <br />
    forks = {{ forks_ang }} <br />
    emb: <br />
    stargazers = {{ stargazers_emb }} <br />
    subscribers = {{ subscribers_emb }} <br />
    forks = {{ forks_emb }} <br />
    rea: <br />
    stargazers = {{ stargazers_rea }} <br />
    subscribers = {{ subscribers_rea }} <br />
    forks = {{ forks_rea }} <br />
    sve: <br />
    stargazers = {{ stargazers_sve }} <br />
    subscribers = {{ subscribers_sve }} <br />
    forks = {{ forks_sve }} <br />
  </div>
</template>

<style></style>

<script>
import axios from "axios";

export default {
  data: function () {
    return {
      message: "Welcome to Vue.js!",
      stargazers_vue: 1,
      stargazers_ang: 2,
      stargazers_emb: 3,
      stargazers_rea: 4,
      stargazers_sve: 5,
      subscribers_vue: 6,
      subscribers_ang: 7,
      subscribers_emb: 8,
      subscribers_rea: 9,
      subscribers_sve: 10,
      forks_vue: 11,
      forks_ang: 12,
      forks_emb: 13,
      forks_rea: 14,
      forks_sve: 15,
    };
  },
  created: function () {
    axios.get("https://api.github.com/repos/vuejs/vue").then((response) => {
      this.stargazers_vue = response.data["stargazers_count"];
      this.subscribers_vue = response.data["watchers_count"];
      this.forks_vue = response.data["forks_count"];
      console.log(response.data);
    });
    // axios
    //   .get("https://api.github.com/repos/angular/angular")
    //   .then((response) => {
    //     this.stargazers_ang = response.data["stargazers_count"];
    //     this.subscribers_ang = response.data["watchers_count"];
    //     this.forks_ang = response.data["forks_count"];
    //     console.log(response.data);
    //   });
    // axios
    //   .get("https://api.github.com/repos/emberjs/ember.js")
    //   .then((response) => {
    //     this.stargazers_emb = response.data["stargazers_count"];
    //     this.subscribers_emb = response.data["watchers_count"];
    //     this.forks_emb = response.data["forks_count"];
    //     console.log(response.data);
    //   });
    // axios
    //   .get("https://api.github.com/repos/facebook/react")
    //   .then((response) => {
    //     this.stargazers_rea = response.data["stargazers_count"];
    //     this.subscribers_rea = response.data["watchers_count"];
    //     this.forks_rea = response.data["forks_count"];
    //     console.log(response.data);
    //   });
    // axios
    //   .get("https://api.github.com/repos/sveltejs/svelte")
    //   .then((response) => {
    //     this.stargazers_sve = response.data["stargazers_count"];
    //     this.subscribers_sve = response.data["watchers_count"];
    //     this.forks_sve = response.data["forks_count"];
    //     console.log(response.data);
    //   });
  },
  methods: {},
};
</script>
