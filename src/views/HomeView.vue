<template>
  <div class="landing-page">
    <div class="title">
      <h1>Guess who tweeted</h1>
    </div>
    <div class="description">
      <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ipsum delectus praesentium et accusamus necessitatibus dolorem minima nulla recusandae, beatae alias nesciunt distinctio est tempore voluptatibus ut, laudantium itaque quidem porro.</p>
    </div>
    <div class="buttons">
      <div class="btn" id="start">Lets start the game!</div>
      <div class="btn" id="about">About me</div>
    </div>
  </div>
</template>

<style scoped>

  .landing-page {
    margin: auto;
    width: 60%;
    padding: 10px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .title {
    margin: 50px 0px;
    font-size: 2rem;
    font-weight: bold;
  }

  .description {
    
  }

  .buttons {
    display: flex;
  }

  .btn {
    border: solid;
    border-width: 3px;
    border-radius: 10px;
    padding: 10px 20px;
    background-color: aqua;
    margin: 5px 5px;
  }


</style>