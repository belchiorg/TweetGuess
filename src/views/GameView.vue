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

let state = reactive({hidden: true})


function handleNextTweet() {
  currentTweetInd++;
  currentTweet = tweets.value[currentTweetInd]
  state.hidden = true;
}

function handleCorrectCompanySelection() {
  state.hidden = false
}

</script>

<template>
  <div class="content">
    <h1 class="index">{{ currentTweetInd+1 }}/{{ tweets.length }}</h1>
    <Tweet :tweet="currentTweet" :handleCorrectCompanySelection="handleCorrectCompanySelection" :hidden="state.hidden"/>
    <div class="btns" v-show="!state.hidden">
      <a :href="currentTweet.link" target="_blank" class="btn" id="show">Go to tweet</a>
      <div  @click="handleNextTweet" class="btn" id="next">Guess next tweet</div>
    </div>
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

.index {
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