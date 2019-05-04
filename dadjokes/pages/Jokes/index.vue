<template>
  <div class="container">
    <div class="row my-5">
      <div class="col-12">
        <SearchJokes v-on:search-text="searchText"/>
      </div>
    </div>
    <div class="row">
      <Joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke"/>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Joke from "../../components/Joke";
import SearchJokes from "../../components/SearchJokes";

export default {
  components: {
    Joke,
    SearchJokes
  },
  data() {
    return {
      jokes: []
    };
  },
  methods: {
    async searchText(text) {
      const config = {
        headers: {
          Accept: "application/json"
        }
      };
      const url = `https://icanhazdadjoke.com/search?term=${text}`;
      try {
        const res = await axios.get(url, config);
        this.jokes = res.data.results;
      } catch (err) {
        console.log(err);
      }
    }
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
