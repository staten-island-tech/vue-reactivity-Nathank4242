<script>
import Thingy from '../components/Thingy.vue'
</script>

<template>
  <header>
    <div class="wrapper">
      <nav>
        <RouterLink to="/">Home</RouterLink>
      </nav>
    </div>
  </header>
  <div class="about flex justify-center bg-cyan-200">
    <h1>Welcome to the page</h1>
  </div>
  <RouterView />
</template>

<style>
body {
  background-color: black;
}
nav {
  font-size: 12px;
}
</style>
