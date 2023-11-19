<script setup>
import Header from '@/components/HeaderApp.vue'
import WeatherInfo from '@/components/WeatherInfo.vue'
import { ref } from 'vue'

const weather = ref(null)
const city = ref('istanbul')
const apiKey = ref('3cc537fa5d844c3aae326f1cd6e25178')

fetch(
  `https://api.openweathermap.org/data/2.5/forecast?q=${city.value}&appid=${apiKey.value}&units=metric`
)
  .then((response) => response.json())
  .then((data) => (weather.value = data.list.slice(0, 21)))
</script>

<template>
  <div id="stars-container">
    <div id="stars"></div>
    <div id="stars2"></div>
    <div id="stars3"></div>
    <Header></Header>
    <WeatherInfo :weather="weather"></WeatherInfo>
  </div>
</template>

<style lang="scss">
@import url(./assets/bg-amination.scss);
</style>
