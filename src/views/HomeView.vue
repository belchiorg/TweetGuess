<script setup>
import { RouterLink } from 'vue-router'
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
      <div class="btn" id="about">About me</div>
      <RouterLink id="start" class="btn" to="/tweet">Lets start the game!</RouterLink>
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
    text-align: center;
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
    text-decoration: none;
    color: #f0f9ff
  }

  #start {
    width: 65%;
    background-color: #1DA1F2;
    color: #020617;
  }

  #start:hover {
    background-color: #0C7BBF;
    color: #020617;
  }

  #about {
    width: 40%;
    background-color: #E1E8ED;
    color: #14171A;
  }

  #about:hover {
    background-color: #AAB8C2;
    color: #020617;
  }


</style>