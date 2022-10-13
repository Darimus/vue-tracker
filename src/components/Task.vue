<template>
  <div class="box has-text-weight-bold">
    <div class="columns">
      <div class="column is-7">Descrição da tarefa</div>
      <div class="column">
        <StopwatchComponent timeInSeconds=15 />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import StopwatchComponent from './stopwatchComponent.vue'

export default defineComponent({
  name: 'TaskComponent',
  component: { StopwatchComponent },
})

</script>

<style scoped>
.box {
  background-color: #faf0ca;
}
</style>