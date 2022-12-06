<template>
  <ul class="grid gap-2 grid-cols-2">
    <li
      class="text-xl flex w-screen justify-between py-2 px-4 bg-red-700 text-white"
    >
      <div class="flex gap-6">
        <div>Equipa</div>
        <router-link to="/projects">Projetos</router-link>
      </div>
      <div>
        <router-link to="/">NI Logo</router-link>
      </div>
      <div class="flex gap-6">
        <div>Eventos</div>
        <div>Contactos</div>
      </div>
    </li>
  </ul>
</template>

<script lang="ts">
export default {};
</script>
