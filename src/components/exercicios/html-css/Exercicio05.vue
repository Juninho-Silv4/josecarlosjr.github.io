<script setup lang="ts">
  defineOptions({
    name: 'ExercicioCinco',
  })

  const txt1 = 'Trabalhando com listas';
  const txt2 = 'Listas ordenadas';
  const txt3 = 'Listas não ordenadas';
  const txt4 = 'Juntando listas versão 1.0';
  const txt5 = 'Meus jogos favoritos';
  const txt6 = 'Lista de definição';

  const list1 = [
    'Acordar',
    'Ligar para o João',
    'Tomar café',
    'Escovar os dentes',
    'Ir para a faculdade',
    'Almoçar',
    'Ir para o trabalho',
    'Voltar para casa',
    'Jantar',
    'Dormir'
  ];

  const list2 = [
    'Pão',
    'Leite',
    'Tomate',
    'Alface',
    'Manteiga',
    'Arroz',
    'Feijão'
  ];

  const list3 = [
    'Antigas',
    'Novas'
  ];

  const list4 = [
    'PC',
    'Mobile'
  ];

  const list5 = [
    'Genshin Impact',
    'Honkai: Star Rail',
    'Skyrim',
    'The Sims 4',
    'MS',
    'OIHS',
    'CC',
    'LH',
    'PAS',
    'BB'
  ];

  const list6 = [
    'HTML',
    'CSS',
    'JavaScript'
  ];

  const list7 = [
    'Clipper',
    'Visual Basic',
    'Fortran',
    'Delphi',
    'PHP',
    'Python',
    'JavaScript',
    'Kotlin'
  ]

  const list8 = [
    'Linguagem de marcação para criação de um site.',
    'Linguagem de marcação para criação do design de um site.',
    'Linguagem de programação para a criação de interatividade de um site.'
  ];
</script>

<template>
  <div class="mx-auto w-fit space-y-4 text-left">
    <h1 class="text-center text-2xl font-bold">{{ txt1 }}</h1>

    <div class="w-fit">
      <h2 class="text-xl font-semibold">{{ txt2 }}</h2>
      <ol class="list-decimal pl-6">
        <li v-for="item in list1" :key="item">{{ item }}</li>
      </ol>
    </div>

    <div class="w-fit">
      <h2 class="text-xl font-semibold">{{ txt3 }}</h2>
      <ul class="list-[square] pl-6">
        <li v-for="item in list2" :key="item">{{ item }}</li>
      </ul>
    </div>

    <div class="w-fit">
      <h2 class="text-xl font-semibold">{{ txt4 }}</h2>
      <ol class="list-decimal pl-6">
        <li v-for="item in list3" :key="item"><p class="font-semibold">{{ item }}</p>
          <ol class="list-[lower-alpha] pl-6">
            <li v-for="language in list7.slice(0, 4)" :key="language">{{ language }}</li>
          </ol>
        </li>
        <li v-for="item in list4" :key="item"><p class="font-semibold">{{ item }}</p>
          <ol class="list-[lower-alpha] pl-6" start="5">
            <li v-for="language in list7.slice(4)" :key="language">{{ language }}</li>
          </ol>
        </li>
      </ol>
    </div>

    <div class="w-fit">
      <h2 class="text-xl font-semibold">{{ txt5 }}</h2>
      <ol class="list-decimal pl-6">
        <li v-for="item in list4" :key="item"><p class="font-semibold">{{ item }}</p>
          <ul class="list-[square] pl-6">
            <li v-for="game in list5" :key="game">{{ game }}</li>
          </ul>
        </li>
      </ol>
    </div>

    <div class="w-fit">
      <h2 class="text-xl font-semibold">{{ txt6 }}</h2>
      <dl>
        <template v-for="(language, index) in list6" :key="language">
          <dt class="font-semibold">{{ language }}</dt>
          <dd class="mb-2">{{ list8[index] }}</dd>
        </template>
      </dl>
    </div>
  </div>
</template>
