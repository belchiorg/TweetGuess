<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div class="landing-page">
    <div class="title">
      <h1>Guess who tweeted</h1>
    </div>
    <div class="description">
      <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ipsum delectus praesentium et accusamus necessitatibus dolorem minima nulla recusandae, beatae alias nesciunt distinctio est tempore voluptatibus ut, laudantium itaque quidem porro.</p>
    </div>
    <div class="buttons">
      <RouterLink id="start" class="btn" to="/tweet">Lets start the game!</RouterLink>
      <div class="btn" id="about">About me</div>
    </div>
  </div>
</template>

<style scoped>

  .landing-page {
    margin: 2.5rem auto;
    width: 60%;
    padding: 10px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .title {
    margin: 50px 0px 20px 0px;
    font-size: 2rem;
    font-weight: bold;
    text-align: center;
  }

  .description {
    font-size: 1.2rem;
    text-align: justify;
  }

  .buttons {
    margin: 20px 0px;
    display: flex;
    width: 100%;
  }

  .btn {
    text-align: center;
    height: fit-content;
    border: solid;
    border-width: 3px;
    border-radius: 10px;
    padding: 10px 20px;
    margin: 0px 5px;
  }

  #start {
    width: 60%;
    background-color: aqua;
  }

  #about {
    width: 40%;
    background-color: rgba(128, 128, 128, 0.1);
  }


</style>