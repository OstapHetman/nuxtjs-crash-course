<template>
  <div class="container">
    <div class="row">
      <div class="col-12">
        <nuxt-link to="/jokes" class="btn btn-secondary">Back to Jokes</nuxt-link>
      </div>
      <div class="col-8 mx-auto mt-5">
        <h2 class="text-muted">{{ joke }}</h2>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      joke: {}
    };
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    };
    const url = `https://icanhazdadjoke.com/j/${this.$route.params.id}`;
    try {
      const res = await axios.get(url, config);
      this.joke = res.data.joke;
    } catch (err) {
      console.log(err);
    }
  },
  head() {
    return {
      title: this.joke,
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Best place for jokes"
        }
      ]
    };
  }
};
</script>

<style>
</style>
