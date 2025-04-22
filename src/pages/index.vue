<script setup lang="ts">
import { supabase } from '@/lib/supabaseClient';

// Inmediately invoked function expression, it will self invoke when the code gets here
// It can also be normal anonymous function

;(async () => {
  const { data, error } = await supabase.from('projects').select()

  if (error) console.log(error)

  console.log('Projects : ', data)
})()

</script>

<template>
  <main>
    <h1>Home Page</h1>
    <RouterLink :to="{ name: '/projects/[id]', params: { id: 1 } }">Go to project 1</RouterLink>
  </main>
</template>

<style scoped></style>
