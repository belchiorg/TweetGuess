<script setup>
import { ref } from 'vue';
import Tweet from '../Components/Tweet.vue'

import tweetsJson from '../data/Tweets.json'

const tweets = ref(tweetsJson)

let tweet = tweets[0]

</script>

<template>
  <div class="content">
    <Tweet :tweet.name="name"/>
  </div>
</template>

