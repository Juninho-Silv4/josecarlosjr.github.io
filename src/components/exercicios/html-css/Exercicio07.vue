<script setup lang="ts">
  defineOptions({
    name: 'ExercicioSete',
  })

  const baseUrl = import.meta.env.BASE_URL;
</script>

<template>
  <div class="w-full space-y-4 text-center">
    <h1 class="text-2xl font-bold">Imagem dinâmica</h1>

    <p>
      Tente abrir esse site em vários dispositivos diferentes ou simplesmente aumente e diminua o tamanho do navegador.
    </p>

    <picture>
      <source media="(min-width: 1050px)" :srcset="`${baseUrl}exercises/html-css/ex07/imagens/grande.png`" type="image/png" />
      <source media="(min-width: 750px)" :srcset="`${baseUrl}exercises/html-css/ex07/imagens/media.png`" type="image/png" />
      <source media="(min-width: 350px)" :srcset="`${baseUrl}exercises/html-css/ex07/imagens/pequena.png`" type="image/png" />
      <img class="max-w-full" :src="`${baseUrl}exercises/html-css/ex07/imagens/grande.png`" alt="Imagem flexível" />
    </picture>

    <h1 class="text-2xl font-bold">Reproduzindo áudios</h1>
    <p>Aprendendo a reproduzir áudios em HTML5.</p>

    <audio class="w-full" preload="metadata" controls>
      <source :src="`${baseUrl}exercises/html-css/ex07/media/bach-cello.mp3`" type="audio/mpeg" />
      Seu navegador não suporta áudio HTML5.
    </audio>
  </div>
</template>
