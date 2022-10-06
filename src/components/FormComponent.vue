<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="Formulário para criação de uma nova tarega">
        <input type="text" class="input" placeholder="Qual tarefa você deseja iniciar?">
      </div>

      <div class="column">
        <div class="is-flex is-align-items-center is-justify-content-space-between">
          <section>
            <strong>{{ elapsedTime }}</strong>
          </section>

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
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: "FormComponent",
  data() {
    return {
      timeInSeconds: 0,
      referenceForStop: 0
    }
  },

  computed: {
    elapsedTime(): string {
      return new Date(this.timeInSeconds * 1000).toISOString().substr(11, 8);
    }
  },

  methods: {
    start() {
      this.referenceForStop = setInterval(() => {
        this.timeInSeconds += 1
      }, 1000)
    },

    pause() {
      clearInterval(this.referenceForStop)
    },

    stop() {
      clearInterval(this.referenceForStop)
    }
  }
})
</script>

<style>

</style>