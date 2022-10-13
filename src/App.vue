<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <SideBar></SideBar>
    </div>
    <div class="column is-three-quarter">
      <FormComponent></FormComponent>
      <div class="lista">
        <TaskComponent></TaskComponent>
        <TaskComponent></TaskComponent>
        <TaskComponent></TaskComponent>
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import SideBar from './components/SideBar.vue';
import FormComponent from './components/FormComponent.vue'
import TaskComponent from './components/Task.vue';

export default defineComponent({
  name: "App",
  components: {
    SideBar,
    FormComponent,
    TaskComponent
  }
});
</script>

<style>
.lista {
  padding: 1.25rem;
}
</style>
