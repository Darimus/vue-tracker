<template>
  <div class="is-flex is-align-items-center is-justify-content-space-between">

    <StopwatchComponent :timeInSeconds="timeInSeconds"></StopwatchComponent>

    <button class="button" @click="start">
      <span class="icon">
        <i class="fas fa-play"></i>
      </span>
      <span>play</span>
    </button>

    <button class="button" @click="pause">
      <span class="icon">
        <i class="fas fa-pause"></i>
      </span>
      <span>pause</span>
    </button>

    <button class="button" @click="stop">
      <span class="icon">
        <i class="fas fa-stop"></i>
      </span>
      <span>stop</span>
    </button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import StopwatchComponent from './stopwatchComponent.vue'

export default defineComponent({
  name: "TimerComponent",
  components: { StopwatchComponent },
  data() {
    return {
      timeInSeconds: 0,
      referenceForStop: 0
    };
  },
  methods: {
    start() {
      this.referenceForStop = setInterval(() => {
        this.timeInSeconds += 1;
      }, 1000);
    },
    pause() {
      clearInterval(this.referenceForStop);
    },
    stop() {
      clearInterval(this.referenceForStop);
    }
  }
})
</script>