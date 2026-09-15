<script setup lang="ts">
  defineOptions({
    name: 'ExercicioTres',
  })

  const baseUrl = import.meta.env.BASE_URL;
  const txt1 = 'Testando imagens e favicon!';
  const txt2 = 'Testando upload de imagens com HTML!';
  const txt3 = 'Podemos adicionar imagens pelo caminho da máquina:';
  const txt4 = 'Também podemos adicionar imagens por link:';

  const img: Array<{ src: string; alt: string }> = [
    {
      src: `${baseUrl}exercises/html-css/ex03/Scarlet_Witch_(MoM)-200.png`,
      alt: 'Feiticeira Escarlate',
    },
    {
      src: 'https://lumiere-a.akamaihd.net/v1/images/feiticeira_escarlate_ucm_4_c584f237.jpeg?region=0,0,1280,720&width=960',
      alt: 'Feiticeira Escarlate Cartoon',
    },
  ]
</script>

<template>
  <div class="w-full space-y-4 text-center">
    <h1 class="text-2xl font-bold">{{ txt1 }}</h1>
    <p>{{ txt2 }}</p>
    <p>{{ txt3 }}</p>
    <img
      class="max-w-full text-center mx-auto"
      :src="img[0]!.src"
      :alt="img[0]!.alt"
    />
    <p>{{ txt4 }}</p>
    <img
      class="max-w-full w-150 text-center mx-auto"
      :src="img[1]!.src"
      :alt="img[1]!.alt"
    />
  </div>
</template>
