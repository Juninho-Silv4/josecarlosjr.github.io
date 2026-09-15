<script setup lang="ts">
  defineOptions({
    name: 'ExercicioQuatro',
  })

  const txt1 = 'Principais formatações';
  const txt2 = 'Negrito / Destaque';
  const txt3 = 'Itálico / Ênfase';
  const txt4 = 'Texto marcado';
  const txt5 = 'Texto grande e pequeno';
  const txt6 = 'Texto deletado';
  const txt7 = 'Texto inserido';
  const txt8 = 'Texto sobrescrito';
  const txt9 = 'Texto subscrito';
  const parag1 = 'Nessa frase temos um termo em negrito';
  const parag2 = 'usando as tags <b> e </b>';
  const parag3 = ' não semânticas!';

</script>

<template>
  <div class="w-full space-y-4 text-center">
    <h1 class="text-2xl font-bold">{{ txt1 }}</h1>

    <h2 class="text-xl font-semibold">{{ txt2 }}</h2>
    <p>{{ parag1 }}
      <b class="font-bold">
        {{ parag2 }}
      </b>
      {{ parag3 }}
    </p>

    <h2 class="text-xl font-semibold">{{ txt3 }}</h2>
    <p>Nesta frase, temos um termo em itálico <i>com a tag i</i>.</p>
    <p>Nesta frase, temos um <em>termo em ênfase</em> usando a tag ênfase.</p>

    <h2 class="text-xl font-semibold">{{ txt4 }}</h2>
    <p>Podemos criar também <mark>um texto marcado</mark> com a tag mark.</p>

    <h2 class="text-xl font-semibold">{{ txt5 }}</h2>
    <p>Estou criando um <big>texto grande</big> e um <small>texto pequeno</small>.</p>

    <h2 class="text-xl font-semibold">{{ txt6 }}</h2>
    <p>Podemos marcar <del>um texto como excluído</del> para indicar que ele deve ser lido, mas não considerado!</p>

    <h2 class="text-xl font-semibold">{{ txt7 }}</h2>
    <p>Podemos marcar <ins>um texto como inserido</ins> para dar uma ênfase e indicar que ele foi adicionado depois!</p>
    <p>Existe também o <u>sublinhado com a tag u</u> (não semântica).</p>

    <h2 class="text-xl font-semibold">{{ txt8 }}</h2>
    <p>Para inserir coisas do tipo x<sup>20</sup>+3.</p>

    <h2 class="text-xl font-semibold">{{ txt9 }}</h2>
    <p>Para inserir coisas do tipo x<sub>20</sub>+3.</p>
  </div>
</template>
