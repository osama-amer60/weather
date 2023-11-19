<script setup>
import { ref, defineEmits } from 'vue'
const emit = defineEmits(['city-name'])

const searchInput = ref()

const emitCustomEvent = () => {
  emit('city-name', searchInput.value)
}
</script>
<template>
  <header>
    <nav>
      <div class="container-fluid text-white pt-5 pb-3">
        <div class="row">
          <div class="col-12 col-md-1"></div>
          <div class="col-12 col-md-4">
            <!-- Nav tabs -->
            <ul class="nav ms-3 ps-3">
              <li class="me-4">
                <button>Now</button>
              </li>
              <li class="me-4">
                <button>Hourly</button>
              </li>
              <li class="active">
                <button>Days</button>
              </li>
            </ul>
          </div>
          <div class="col-12 col-md-2">
            <div class="input-group mb-3">
              <input
                type="text"
                class="form-control"
                placeholder="City's Name"
                aria-label="City's Name"
                aria-describedby="button-addon2"
                v-model="searchInput"
              />
              <button
                class="btn btn-primary"
                type="button"
                id="button-addon2"
                @click="emitCustomEvent"
              >
                Search
              </button>
            </div>
          </div>
        </div>
      </div>
    </nav>
  </header>
</template>
