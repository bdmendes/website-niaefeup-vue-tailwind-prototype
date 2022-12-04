<script lang="ts">
import { RouterView } from 'vue-router'
import NavBar from './components/NavBar.vue'

export default {
  components: {
    NavBar,
    RouterView,
  },
}
</script>

<template>
  <div class="flex flex-col min-h-screen">
    <header class="fixed">
      <NavBar />
    </header>

    <div id="content" class="px-4 py-20 bg-gradient-to-b from-red-700 to-red-900 flex-1 text-white">
      <RouterView />
    </div>

    <footer>
      <div class="text-center py-4">
        <p>© 2021 Núcleo de Informática</p>
      </div>
    </footer>
  </div>
</template>

<style scoped>

</style>