<script setup lang="ts">
import { supabase } from '@/lib/supabaseClient'
import { ref } from 'vue'
import type { Tables } from '../../../database/database.types';

const projects = ref<Tables<'projects'>[] | null>(null)

// Inmediately invoked function expression, it will self invoke when the code gets here
// It can also be normal anonymous function
;(async () => {
  const { data, error } = await supabase.from('projects').select()

  if (error) console.log(error)

  projects.value = data
})()
</script>

<template>
  <main>
    <h1>Projects Page</h1>
    <RouterLink to="/">Go to home</RouterLink>
    <ul>
      <li v-for="project in projects" :key="project.id">{{ project.name }}</li>
    </ul>
  </main>
</template>

<style scoped></style>
