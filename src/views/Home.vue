<template>
  <div class="home">
    <h1>{{ message }}</h1>
  </div>
</template>

<style></style>

<script>
export default {
  data: function () {
    return {
      message: "Welcome to Vue.js!",
      stargazers_vue: []
      stargazers_ang: []
      stargazers_emb: []
      stargazers_rea: []
      stargazers_sve: []
      subscribers_vue: []
      subscribers_ang: []
      subscribers_emb: []
      subscribers_rea: []
      subscribers_sve: []
      forks_vue: []
      forks_ang: []
      forks_emb: []
      forks_rea: []
      forks_sve: []
    };
  },
  created: function () {},
  methods: {},
};
</script>
https://api.github.com/repos/vuejs/vue/stargazers
