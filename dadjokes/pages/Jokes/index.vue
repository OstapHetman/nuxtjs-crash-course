<template>
  <div class="container">
    <div class="row">
      <Joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke"/>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Joke from "../../components/Joke";

export default {
  components: {
    Joke
  },
  data() {
    return {
      jokes: []
    };
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    };
    const url = " https://icanhazdadjoke.com/search";
    try {
      const res = await axios.get(url, config);
      this.jokes = res.data.results;
    } catch (err) {
      console.log(err);
    }
  },
  head() {
    return {
      title: "Dad Jokes!",
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
