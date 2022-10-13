<template>
  <div class="is-flex is-align-items-center is-justify-content-space-between">

    <StopwatchComponent :timeInSeconds="timeInSeconds"></StopwatchComponent>

    <button class="button" @click="start" :disabled="timerStart">
      <span class="icon">
        <i class="fas fa-play"></i>
      </span>
      <span>play</span>
    </button>

    <button class="button" @click="stop" :disabled="!timerStart">
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
  emits: ['timerFinish'],
  components: { StopwatchComponent },
  data() {
    return {
      timeInSeconds: 0,
      referenceForStop: 0,
      timerStart: false
    };
  },
  methods: {
    start() {
      this.timerStart = true
      this.referenceForStop = setInterval(() => {
        this.timeInSeconds += 1;
      }, 1000);
    },

    stop() {
      this.timerStart = false;
      clearInterval(this.referenceForStop);
      this.$emit('timerFinish', this.timeInSeconds);
      this.timeInSeconds = 0;
    }
  }
})
</script>