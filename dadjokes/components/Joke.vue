<template>
  <div class="col-4">
    <div class="card text-white bg-secondary mb-3">
      <div class="card-body">
        <p class="card-text">{{ joke }}</p>
      </div>
      <div class="card-footer bg-transparent border-light">
        <nuxt-link :to="'jokes/' + id" class="btn btn-light">View</nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Joke",
  props: ["joke", "id"]
};
</script>

