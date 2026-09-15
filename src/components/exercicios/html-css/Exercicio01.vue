<script setup lang="ts">
  defineOptions({
    name: 'ExercicioUm',
  })

  const txt1 = 'Meu primeiro exercício!'
  const txt2 = 'Este é o meu primeiro exercício!'
</script>

<template>
  <div class="w-full space-y-4 text-center">
    <h1 class="text-2xl font-bold">{{ txt1 }}</h1>
    <p>{{ txt2 }}</p>
  </div>
</template>
