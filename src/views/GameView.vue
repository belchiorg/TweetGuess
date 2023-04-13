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
    <Tweet :tweet="currentTweet" :handleCorrectCompanySelection="handleCorrectCompanySelection" :hidden="state.hidden"/>
  </div>
</template>
