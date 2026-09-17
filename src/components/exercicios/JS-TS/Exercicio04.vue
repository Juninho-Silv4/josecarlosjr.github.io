<script setup lang="ts">
import { ref } from 'vue'

defineOptions({ name: 'ExercicioQuatro' })

const numero = ref<number | null>(null)

type Tabuada = {
  numero: number
  resultados: number[]
}

const tabuadas = ref<Tabuada[]>([])
const limiteTabuadas = 5

function calcularTabuada() {
  if (numero.value === null || !Number.isFinite(numero.value)) {
    return
  }

  const numeroAtual = numero.value

  const novaTabuada: Tabuada = {
    numero: numeroAtual,
    resultados: Array.from({ length: 10 }, (_, indice) => numeroAtual * (indice + 1)),
  }

  tabuadas.value = [...tabuadas.value, novaTabuada].slice(-limiteTabuadas)
}

const txt1 = 'Tabuada'
const txt2 = 'Digite um número'
const txt3 = 'Calcular'
</script>

<template>
  <div class="w-full space-y-4 text-center">
    <h1 class="text-2xl font-bold">{{ txt1 }}</h1>
    <label class="flex flex-col items-center gap-2" for="numero">
      {{ txt2 }}
      <input id="numero" v-model.number="numero" class="input input-bordered" type="number" />
    </label>
    <button class="btn btn-primary" type="button" @click="calcularTabuada">{{ txt3 }}</button>
    <div
      v-if="tabuadas.length"
      class="mx-auto grid max-w-6xl grid-cols-1 justify-items-center gap-6 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-5"
      aria-live="polite"
    >
      <ul
        v-for="(tabuada, indiceTabuada) in tabuadas"
        :key="`${tabuada.numero}-${indiceTabuada}`"
        class="mx-auto w-fit text-left"
      >
        <li v-for="(resultado, indice) in tabuada.resultados" :key="indice">
          {{ tabuada.numero }} × {{ indice + 1 }} = {{ resultado }}
        </li>
      </ul>
    </div>
  </div>
</template>
