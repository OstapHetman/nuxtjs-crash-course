<template>
  <nav class="navbar navbar-expand-md navbar-dark bg-dark mb-4">
    <a class="navbar-brand" href="#">Jokes</a>
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#navbarCollapse"
      aria-controls="navbarCollapse"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarCollapse">
      <ul class="navbar-nav ml-auto">
        <li class="nav-item">
          <nuxt-link to="/" class="nav-link">Home</nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link to="/about" class="nav-link">About</nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link to="/jokes" class="nav-link">Jokes</nuxt-link>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: "AppHeader"
};
</script>