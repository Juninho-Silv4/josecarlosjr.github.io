<script setup lang="ts">
  defineOptions({
    name: 'ExercicioCinco',
  })
</script>

<template>
  <div class="w-full space-y-4 text-center">
    <h1 class="text-2xl font-bold">Trabalhando com listas</h1>

    <h2 class="text-xl font-semibold">Listas ordenadas</h2>
    <ol class="list-decimal pl-6">
      <li>Acordar</li>
      <li>Ligar para o João</li>
      <li>Tomar café</li>
      <li>Escovar os dentes</li>
      <li>Ir para a faculdade</li>
      <li>Almoçar</li>
      <li>Ir para o trabalho</li>
      <li>Voltar para casa</li>
      <li>Jantar</li>
      <li>Dormir</li>
    </ol>

    <h2 class="text-xl font-semibold">Listas não ordenadas</h2>
    <ul class="list-[square] pl-6">
      <li>Pão</li>
      <li>Leite</li>
      <li>Tomate</li>
      <li>Alface</li>
      <li>Manteiga</li>
      <li>Arroz</li>
      <li>Feijão</li>
    </ul>

    <h2 class="text-xl font-semibold">Juntando listas versão 1.0</h2>
    <ol class="list-decimal pl-6">
      <li>Antigas
        <ol class="list-[lower-alpha] pl-6">
          <li>Clipper</li>
          <li>Visual Basic</li>
          <li>Fortran</li>
          <li>Delphi</li>
        </ol>
      </li>
      <li>Novas
        <ol class="list-[lower-alpha] pl-6" start="5">
          <li>PHP</li>
          <li>Python</li>
          <li>JavaScript</li>
          <li>Kotlin</li>
        </ol>
      </li>
    </ol>

    <h2 class="text-xl font-semibold">Meus jogos favoritos</h2>
    <ol class="list-decimal pl-6">
      <li>PC
        <ul class="list-[square] pl-6">
          <li>Genshin Impact</li>
          <li>Honkai: Star Rail</li>
          <li>Skyrim</li>
          <li>The Sims 4</li>
          <li>MS</li>
        </ul>
      </li>
      <li>Mobile
        <ul class="list-[square] pl-6">
          <li>OIHS</li>
          <li>CC</li>
          <li>LH</li>
          <li>PAS</li>
          <li>BB</li>
        </ul>
      </li>
    </ol>

    <h2 class="text-xl font-semibold">Lista de definição</h2>
    <dl>
      <dt class="font-semibold">HTML</dt>
      <dd>Linguagem de marcação para criação de um site.</dd>
      <dt class="font-semibold">CSS</dt>
      <dd>Linguagem de marcação para criação do design de um site.</dd>
      <dt class="font-semibold">JavaScript</dt>
      <dd>Linguagem de programação para a criação de interatividade de um site.</dd>
    </dl>
  </div>
</template>
