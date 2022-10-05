<template>
  <header>
    <h1>
      <img class="sidebar-logo" src="../assets/logo.png" alt="Logo da Tracker">
    </h1>
  </header>
</template>

<script lang="ts">
  import { defineComponent } from 'vue';

  export default defineComponent({
    name: "SideBar"
  })
</script>

<style scoped>
header {
  padding: 1rem;
  background: #0d3b66;
  width: 100%;
  height: 100vh;

}
.sidebar-logo {
  width: 110px;
  height: 110px;
}

@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
</style>