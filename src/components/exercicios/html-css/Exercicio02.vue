<script setup lang="ts">
  defineOptions({
    name: 'ExercicioDois',
  })

  const txt1 = 'Parágrafos e Quebras de Linha';
  const txt2 = 'Você pode escrever um parágrafo de qualquer jeito, basta deixar tudo dentro das tags:';
  const txt3 = 'Para quebrar o texto em algum lugar desejado, use a tag';
  const txt4 = 'Vamos adicionar alguns símbolos especiais:';

</script>

<template>
  <div class="w-full space-y-4 text-center">
    <h1 class="text-2xl font-bold">{{ txt1 }}</h1>

    <hr class="w-full border-base-300" />

    <p>
      {{ txt2 }}
      <code>&lt;p&gt; &amp; &lt;/p&gt;</code>
    </p>

    <p>
      {{ txt3 }}
      <code>&lt;br&gt;</code>.
    </p>

    <p>
      {{ txt4 }}<br />
      &reg; &copy; &trade; &euro; &pound; &yen; &cent; &Delta; &uarr;
    </p>
  </div>
</template>
