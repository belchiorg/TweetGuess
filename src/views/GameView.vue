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
      <a href="https://google.com" target="_blank"><button>Show</button></a>
      <button  @click="handleNextTweet">Next</button>
    </div>
  </div>
</template>

<style>
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
</style>