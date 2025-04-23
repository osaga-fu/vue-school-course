<script setup lang="ts">

</script>

<template>
  <main>
    <h1>Home Page</h1>
    <RouterLink :to="{ name: '/projects/[id]', params: { id: 1 } }">Go to project 1</RouterLink>
  </main>
</template>

<style scoped></style>
