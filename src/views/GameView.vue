<script setup>
import { reactive, ref } from 'vue';
import Tweet from '../Components/Tweet.vue'

import tweetsJson from '../data/Tweets.json'

const tweets = ref(tweetsJson)

function shuffle(array) {
  for (let i = array.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [array[i], array[j]] = [array[j], array[i]];
  }
  return array;
}

shuffle(tweets.value);

let currentTweetInd = 0;
let currentTweet = tweets.value[currentTweetInd]

let state = reactive({
  hidden: true,
  isEndGame: false
})

let wrongAnswers = ref(0);

function incWrongAnswers() {
  wrongAnswers.value++;
}

function handleNextTweet() {
  currentTweetInd++;
  if (currentTweetInd <= tweets.value.length) {
    currentTweet = tweets.value[currentTweetInd]
    state.hidden = true;
  }
  else {
    state.isEndGame = true
  }
}

function handleCorrectCompanySelection() {
  state.hidden = false
}

function getFinalMessage() {
  if (wrongAnswers.value <= 10) {
    return `You've finished with a total of ${wrongAnswers.value} wrong guesses! That's amazing!`
  }
  return `You had a total of ${wrongAnswers.value} wrong guesses. That's kinda weak, I'm ngl :P`
}

</script>

<template>
  <div v-if="!state.isEndGame" class="content">
    <h1 class="title">{{ currentTweetInd+1 }}/{{ tweets.length }}</h1>
    <Tweet :tweet="currentTweet" :handleCorrectCompanySelection="handleCorrectCompanySelection" :hidden="state.hidden" :incWrongAnswers="incWrongAnswers"/>
    <div class="btns" v-show="!state.hidden">
      <a :href="currentTweet.link" target="_blank" class="btn" id="show">Go to tweet</a>
      <div  @click="handleNextTweet" class="btn" id="next">Guess next tweet</div>
    </div>
    <h3 v-show="wrongAnswers > 0">Wrong answers: {{ wrongAnswers }}</h3>
  </div>
  <div v-else class="content final">
    <h1 class="title">Congrats! You finished the game!</h1>
    <h2 class="description">You've guessed every tweet on this game! {{ getFinalMessage() }} I hope you had fun playing this. I'd really appreciate if you could give me your opinion.</h2>

  </div>
</template>

<style scoped>
.content {
  margin: 2.5rem auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.final {
  width: 50%;
}

.title {
  margin: 40px 0px 20px 0px;
  font-size: 2rem;
  font-weight: bold;
  text-align: center;
}

.btns {
  width: 50%;
  max-width: 700px;
  display: flex;
  justify-content: space-between;
  margin: 20px 0px;
}

.description {
    font-size: 1.2rem;
    text-align: center;
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

  #show {
    width: 40%;
    background-color: #E1E8ED;
    color: #020617;
    
  }

  #next {
    width: 60%;
    background-color: #1DA1F2;
    color: #020617;
  }

  #show:hover {
    background-color: #B3BCC1;
    color: #020617;
  }

  #next:hover {
    background-color: #0C7BBF;
    color: #020617;
  }
</style>