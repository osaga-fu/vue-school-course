<script setup lang="ts">
import { useRoute } from "vue-router";

const route = useRoute()

</script>

<template>
  <main>
    <h1>Project {{ route.params?.id }}</h1>
  </main>
</template>

<style scoped></style>
