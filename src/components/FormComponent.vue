<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="Formulário para criação de uma nova tarega">
        <input type="text" class="input" placeholder="Qual tarefa você deseja iniciar?" v-model="descriptionTask">
      </div>

      <div class="column">
        <TimerComponent @timerFinish="finishTask"></TimerComponent>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import TimerComponent from './timer.vue'

export default defineComponent({
  name: "FormComponent",
  components: { TimerComponent },
  data() {
    return {
      descriptionTask: ''
    }
  },

  methods: {
    finishTask(timeInSeconds: number): void {
      console.log('Tempo decorrdio: ', timeInSeconds);
      console.log('Descrição da tarefa:', this.descriptionTask);
      this.descriptionTask = '';
    }
  }
})
</script>

<style>

</style>