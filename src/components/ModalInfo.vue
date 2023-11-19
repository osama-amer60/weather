<script setup>
const props = defineProps({
  ModalWeather: {
    type: Object,
    required: true
  }
})
const getDayName = (date) => {
  var dateObject = new Date(date)
  var dayOfWeek = dateObject.getDay()
  var daysOfWeek = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday']
  var dayName = daysOfWeek[dayOfWeek]

  return dayName
}
</script>

<template>
  <!-- Modal -->
  <div
    class="modal fade"
    id="exampleModal"
    tabindex="-1"
    aria-labelledby="exampleModalLabel"
    aria-hidden="true"
  >
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h1 class="modal-title fs-5" id="exampleModalLabel">
            {{ getDayName(props?.ModalWeather?.dt_txt) }}
          </h1>
          <button
            type="button"
            class="btn-close"
            data-bs-dismiss="modal"
            aria-label="Close"
          ></button>
        </div>
        <div class="modal-body">
          <div class="container">
            <div class="row gy-3">
              <div class="col-6">Data - Time</div>
              <div class="col-6 text-end">
                {{ ModalWeather.dt_txt }}
              </div>
              <div class="col-6">Temperature</div>
              <div class="col-6 text-end">
                {{ ModalWeather?.main?.temp }}
                <span class="fs-6">°</span>
              </div>
              <div class="col-6">Feels Like</div>
              <div class="col-6 text-end">
                {{ ModalWeather?.main?.feels_like }}
                <span class="fs-6">°</span>
              </div>
              <div class="col-6">Temperature Min</div>
              <div class="col-6 text-end">
                {{ ModalWeather?.main?.temp_min }}
                <span class="fs-6">°</span>
              </div>
              <div class="col-6">Temperature Max</div>
              <div class="col-6 text-end">
                {{ ModalWeather?.main?.temp_max }}
                <span class="fs-6">°</span>
              </div>
              <div class="col-6">Wind Speed</div>
              <div class="col-6 text-end">{{ ModalWeather?.wind?.speed }} km/h</div>
              <div class="col-6">Humidity</div>
              <div class="col-6 text-end">{{ ModalWeather?.main?.humidity }} %</div>
            </div>
          </div>
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-outline-danger" data-bs-dismiss="modal">
            Close
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
