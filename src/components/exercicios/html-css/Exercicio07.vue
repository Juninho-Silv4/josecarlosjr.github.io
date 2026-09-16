<script setup lang="ts">
  defineOptions({
    name: 'ExercicioSete',
  })

  const baseUrl = import.meta.env.BASE_URL;
  const txt1 = 'Imagem dinâmica';
  const txt2 = 'Tente abrir esse site em vários dispositivos diferentes ou simplesmente aumente e diminua o tamanho do navegador.';
  const txt3 = 'Reproduzindo áudios';
  const txt4 = 'Aprendendo a reproduzir áudios em HTML5.';
  const txt5 = 'Seu navegador não suporta áudio HTML5.';
</script>

<template>
  <div class="w-full space-y-4 text-center">
    <h1 class="text-2xl font-bold">{{ txt1 }}</h1>

    <p>
      {{ txt2 }}
    </p>

    <picture class="mx-auto block w-fit">
      <source media="(min-width: 1050px)" :srcset="`${baseUrl}exercises/html-css/ex07/imagens/grande.png`" type="image/png" />
      <source media="(min-width: 750px)" :srcset="`${baseUrl}exercises/html-css/ex07/imagens/media.png`" type="image/png" />
      <source media="(min-width: 350px)" :srcset="`${baseUrl}exercises/html-css/ex07/imagens/pequena.png`" type="image/png" />
      <img class="mx-auto block max-w-full" :src="`${baseUrl}exercises/html-css/ex07/imagens/grande.png`" alt="Imagem flexível" />
    </picture>

    <h1 class="text-2xl font-bold">{{ txt3 }}</h1>
    <p>{{ txt4 }}</p>

    <audio class="mx-auto block w-full max-w-2xl" preload="metadata" controls>
      <source :src="`${baseUrl}exercises/html-css/ex07/media/bach-cello.mp3`" type="audio/mpeg" />
      {{ txt5 }}
    </audio>
  </div>
</template>
