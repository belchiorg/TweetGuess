<script setup>
  import GuessField from './GuessField.vue'
  import { defineProps } from "vue";

  const props = defineProps({
    handleCorrectCompanySelection: Function,
    tweet: Object,
    hidden: Boolean
  });
</script>

<template>
  <div class="tweet">
    <div class="thead">
      <div class="account">
        <img v-show="!hidden" class="pfp" :src="tweet.logo" alt="profile picture">
        <div class="accat">
          <h3 v-show="!hidden" class="name">{{ tweet.name }}</h3>
          <h3 v-show="!hidden" class="arroba">{{tweet.at}}</h3>
        </div>
      </div>
      <div>
        <img class="TwitterLogo" src="https://www.iconpacks.net/icons/2/free-twitter-logo-icon-2429-thumb.png" alt="TweeterLogo">
      </div>
    </div>
    <div class="tbody">
      <p class="message">{{ tweet.content }}</p>
      <p class="date">{{ tweet.date }}</p>
    </div>
    <hr>
    <div class="tfooter">
      <GuessField :answer="tweet.name" :handleCorrectCompanySelection="handleCorrectCompanySelection"/>
    </div>
  </div>
</template>

<style scoped>
  .tweet {
    display: flex;
    flex-direction: column;
    margin: auto;
    width: 50%;
    max-width: 700px;
    align-items: center;
    border:solid;
    border-color: #657786;
    border-radius: 2rem;
    padding: 5px 0px; 
    background-color: #E1E8ED;
    color: #020617;
  }

  .thead {
    display: flex;
    flex-direction: row;
    width: 95%;
    justify-content: space-between;
  }

  .tbody {
    width: 100%;
    padding: 3px 15px;
    display: flex;
    align-items: center;
    flex-direction: column;
  }

  .account {
    display: flex;
    flex-direction: row;
    width: fit-content;
    align-items: center;
  }

  .accat {
    display: flex;
    flex-direction: column;
  }

  .message {
    margin: 0px 0px;
    width: 95%;
    line-height: normal;
    text-align: justify;
    font-size: 1.5rem;
  }


  h3, .date {
    font-size: 1rem;
  }

  .name {
    font-weight: bold;
  }

  .date, .arroba {
    color: #657786;
  }

  .date {
    margin: 5px 0px 5px 0px;
    width: 95%;
    text-align: justify;
  }

  hr {
    width: 90.25%;
    height: 1px;
    border-color: #657786;
  }

  .tfooter {
    width: 95%;
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 15px;
    margin-bottom: 15px ;
  }

  .thead img {
    border-radius: 100%;
    height: 3.7rem;
    width: 3.7rem;
    margin: 5px 15px;
  }

</style>
