<script setup>
  import comp from '../data/Companies.json'
  import {watch, ref, reactive} from 'vue'
  import JSConfetti from 'js-confetti'
  import { defineProps } from "vue";

  defineProps({
    handleCorrectCompanySelection: Function,
    answer: String
  });


  const jsConfetti = new JSConfetti()

  let search = ref("");
  const companies = ref(comp)
  companies.value.sort((a, b) => a.name.localeCompare(b.name))
  let filteredArr = companies.value

  const state = reactive({isActive: false})

  function atClickCompany(company, answer, func) {
    search.value = ''
    state.isActive = false
    if (company.name.toLowerCase() == answer.toLowerCase()) {
      jsConfetti.addConfetti();
      func();
    }
  }

  watch (search, () => {
    filteredArr = companies.value.filter(company => company.name.toLowerCase().includes(search.value.trim().toLowerCase()))
  })
</script>

<template>
  <input type="text" autocomplete="off" v-model="search" @click="search = ''" @focus="state.isActive=true" id="GuessField">
  <div v-if="state.isActive && (filteredArr)" class="list">
    <div class="company" v-for="company in filteredArr" :key="company.id" @click="atClickCompany(company, answer, handleCorrectCompanySelection)">
      <h3>{{ company.name }}</h3>
    </div>
  </div>
</template>

<style scoped>
  #GuessField {
    width: 95%;
    margin: 0px;
    align-items: center;
    border-radius: 10px;
    border-style: solid;
    border-width: 2px;
    border-color: #657786;
    padding: 0px 10px;
    font-size: 1.4rem;
    text-align: center;
    z-index: 2;
    background-color: #c0c9cf;
  }

  #GuessField:hover {
    background-color: #AAB8C2;
  }

  .list {
    height: fit-content;
    max-height: 180px;
    padding-top: 2.1rem;
    width: 95%;
    border-radius: 10px;
    position: absolute;
    background-color: hsla(207, 14%, 46%, 0.788);
    z-index: 1;
    border-style: solid;
    border-width: 2px;
    overflow-y: scroll;
  }

  .company {
    width: 98%;
    margin: auto;
    align-items: center;
    padding: 0px 10px;
    font-size: 1.4rem;
    text-align: center;
    border-style:solid;
    border-radius: 2px;
    border-width: 1px;
    border-top: 0px;
    border-left: 0px;
    border-right: 0px;
  }

  .company:hover {
    background-color: #AAB8C2;
  }
</style>
