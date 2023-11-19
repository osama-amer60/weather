<script setup>
import Header from '@/components/HeaderApp.vue'
import WeatherInfo from '@/components/WeatherInfo.vue'
import { ref, onMounted } from 'vue'

const weather = ref(null)
const requestError = ref(false)
const city = ref('istanbul')
const apiKey = ref('3cc537fa5d844c3aae326f1cd6e25178')

const fetchWeather = () => {
  fetch(
    `https://api.openweathermap.org/data/2.5/forecast?q=${city.value}&appid=${apiKey.value}&units=metric`
  )
    .then((response) => response.json())
    .then((data) => (weather.value = data.list.slice(0, 21)))
    .catch(() => (requestError.value = 'There Is no Data'))
}

onMounted(() => {
  fetchWeather()
})

const handleCustomEvent = (payload) => {
  city.value = payload
  fetchWeather()
}
</script>

<template>
  <div id="stars-container">
    <div id="stars"></div>
    <div id="stars2"></div>
    <div id="stars3"></div>

    <Header @city-name="handleCustomEvent"></Header>
    <WeatherInfo :weather="weather" :city="city"></WeatherInfo>
  </div>
</template>

<style lang="scss">
@import url('./assets/bg-animation.scss');
</style>
