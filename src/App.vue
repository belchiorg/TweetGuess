<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div class="app">

    <header>
      <div class="wrapper">
        <nav>
          <RouterLink to="/">Home</RouterLink>
          <RouterLink to="/tweet">Game</RouterLink>
          <RouterLink to="/about">About</RouterLink>
        </nav>
      </div>
    </header>

    <RouterView />
  
  </div>
</template>

<style scoped>
  header {
    padding: 0px 0px 10px 0px;
  }

  .wrapper {
    margin: 0px auto;
    width: 100%;
  }

  nav {
    width: 100%;
    display: flex;
    justify-content: center;
    background-color: #1DA1F2;
  }

  nav a {
    text-decoration: none;
    font-size: 1.2rem;
    font-weight: bold;
    margin: 0% 25px;
    color: #F5F8FA;
  }
</style>
