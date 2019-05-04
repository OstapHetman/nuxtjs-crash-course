<template>
  <form class="form-inline mt-2 mt-md-0" @submit.prevent="onSubmit">
    <input
      class="form-control mr-sm-2"
      type="text"
      placeholder="Search"
      aria-label="Search"
      v-model="text"
    >
    <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
  </form>
</template>

<script>
export default {
  name: "SearchJokes",
  data() {
    return {
      text: ""
    };
  },
  methods: {
    onSubmit() {
      this.$emit("search-text", this.text);
      this.text = "";
    }
  }
};
</script>
