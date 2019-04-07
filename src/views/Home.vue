<template>
  <div class="home">
    <h1>All Dogs</h1>
    <div v-for="dog in dogs">
      <h2>{{ dog.name }}</h2>
    </div>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";

export default {
  data: function() {
    return {
      dogs: []
    };
  },
  created: function() {
    axios.get("/api/dogs").then(response => {
      this.dogs = response.data;
    });
  },
  methods: {}
};
</script>
