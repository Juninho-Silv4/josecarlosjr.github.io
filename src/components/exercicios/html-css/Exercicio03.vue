<script setup lang="ts">
const baseUrl = import.meta.env.BASE_URL;
</script>

<template>
  <div class="w-full space-y-4 text-center">
    <h1 class="text-2xl font-bold">Testando imagens e favicon!</h1>
    <p>Testando upload de imagens com HTML!</p>
    <p>Podemos adicionar imagens pelo caminho da máquina:</p>
    <img
      class="max-w-full"
      :src="`${baseUrl}exercises/html-css/ex03/Scarlet_Witch_(MoM)-200.png`"
      alt="Feiticeira Escarlate"
    />
    <p>Também podemos adicionar imagens por link:</p>
    <img
      class="max-w-full"
      src="https://lumiere-a.akamaihd.net/v1/images/feiticeira_escarlate_ucm_4_c584f237.jpeg?region=0,0,1280,720&width=960"
      alt="Feiticeira Escarlate"
    />
  </div>
</template>
