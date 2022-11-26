<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="max-w-7xl mx-auto ">
      <nav class="py-5">
        <RouterLink to="/" class="px-4 py-2 mr-4 bg-indigo-600 hover:bg-indigo-700 rounded text-white">Home</RouterLink>
        <RouterLink to="/skills" class="px-4 py-2 mr-4 bg-indigo-600 hover:bg-indigo-700 rounded text-white" >Skills</RouterLink>
      </nav>
    </div>
  </header>

  <main class="max-w-7xl mx-auto min-h-screen">
    <RouterView />
  </main>
</template>
