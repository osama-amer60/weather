<script setup>
import { ref } from 'vue'
import ModalInfo from '@/components/ModalInfo.vue'
const props = defineProps({
  weather: Array,
  city: String
})
const ModalWeather = ref({})

const handleDateFormate = (date) => {
  const dateObject = new Date(date)
  const formattedDate = dateObject.toISOString().split('T')[0]
  return formattedDate
}
const getDayName = (date) => {
  var dateObject = new Date(date)
  var dayOfWeek = dateObject.getDay()
  var daysOfWeek = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday']
  var dayName = daysOfWeek[dayOfWeek].toUpperCase()

  return dayName
}

const setWeatherDetails = (weatherData) => {
  ModalWeather.value = weatherData
}
</script>

<template>
  <main>
    <section>
      <div class="container-fluid py-md-5">
        <div class="row">
          <div class="col-12 col-md-1"></div>

          <div class="col-12 col-md-11">
            <div class="container-fluid">
              <h1 class="text-white fs-3 mb-3">Days Weather In {{ city.toUpperCase() }}</h1>
              <div class="row g-4">
                <div
                  class="col-12 col-sm-6 col-md-6 col-lg-3 col-xxl-2 card-container"
                  v-for="(weatherData, index) in props.weather"
                  :key="index"
                >
                  <div
                    class="card"
                    @click="setWeatherDetails(weatherData)"
                    data-bs-toggle="modal"
                    data-bs-target="#exampleModal"
                  >
                    <!--card-header-->
                    <div class="card-header d-flex align-items-center justify-content-between">
                      <div>
                        <span class="day me-1 fw-bold fs-5 text-secondary">
                          {{ getDayName(weatherData.dt_txt) }}
                        </span>
                        <span class="date opacity-75 fs-6 d-block d-md-inline-block">
                          {{ handleDateFormate(weatherData.dt_txt) }}</span
                        >
                      </div>
                      <div>
                        <img
                          src="/right-arrow.svg"
                          alt="right-arrow"
                          width="15"
                          height="13"
                          class="me-1"
                        />
                      </div>
                    </div>

                    <!--card-body-->
                    <div class="card-body">
                      <div class="container-fluid">
                        <div class="row pb-3">
                          <div class="col-8">
                            <div class="day-info">
                              <span class="fw-bold text-muted-main">DAY</span>
                              <h3 class="fs-2 text-secondary mb-0 d-flex">
                                {{ weatherData.main.temp }}
                                <span class="fs-3"> °</span>
                              </h3>
                              <span class="fw-bold text-secondary"
                                >{{ weatherData.weather[0].main }}
                              </span>
                            </div>
                          </div>
                          <div class="col-4 d-flex align-items-center justify-content-center">
                            <div>
                              <img
                                src="/sun.webp"
                                alt="sun"
                                width="70"
                                height="70"
                                class="rounded-circle weather-img"
                              />
                            </div>
                          </div>
                        </div>

                        <div class="row mt-4">
                          <div class="col-6">
                            <h4 class="fs-6 text-secondary">Feels Like</h4>
                          </div>
                          <div class="col-6">
                            <h4 class="fs-6 text-secondary text-end">
                              {{ weatherData.main.feels_like }}
                              <span class="fs-6">°</span>
                            </h4>
                          </div>
                          <div class="col-6">
                            <h4 class="fs-6 text-secondary">Humidity</h4>
                          </div>
                          <div class="col-6">
                            <h4 class="fs-6 text-secondary text-end">
                              {{ weatherData.main.humidity }} %
                            </h4>
                          </div>
                          <div class="col-6">
                            <h4 class="fs-6 text-secondary">Wind</h4>
                          </div>
                          <div class="col-6">
                            <h4 class="fs-6 text-secondary text-end">
                              {{ weatherData.wind.speed }} km/h
                            </h4>
                          </div>
                        </div>
                      </div>
                    </div>

                    <!--card-footer-->
                    <div
                      class="card-footer d-flex align-items-center justify-content-center fw-bold"
                    >
                      <i class="bi bi-clock me-1"></i>
                      <span class="text-muted-main"> Hourly </span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <ModalInfo :ModalWeather="ModalWeather"></ModalInfo>
      </div>
    </section>
  </main>
</template>
