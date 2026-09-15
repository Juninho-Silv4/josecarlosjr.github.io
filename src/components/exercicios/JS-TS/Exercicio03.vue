<script setup lang="ts">
import { ref } from 'vue'

defineOptions({
  name: 'ExercicioTres',
})

const inicio = ref<number | null>(null)
const fim = ref<number | null>(null)
const passo = ref<number | null>(null)
const resultado = ref('Informe início, fim e passo para contar.')

function contar() {
  if (inicio.value === null || fim.value === null || !passo.value || passo.value < 0) {
    resultado.value = 'Preencha os campos com valores válidos.'
    return
  }

  const intervalo = passo.value
  const valores: number[] = []
  const direcao = inicio.value <= fim.value ? 1 : -1

  for (let valor = inicio.value; direcao === 1 ? valor <= fim.value : valor >= fim.value; valor += intervalo * direcao) {
    valores.push(valor)
  }

  resultado.value = valores.join(' → ')
}
</script>

<template>
  <div class="w-full space-y-4 text-center">
    <h1 class="text-2xl font-bold">Contador</h1>
    <div class="flex flex-wrap justify-center gap-3">
      <input v-model.number="inicio" class="input input-bordered w-28" type="number" placeholder="Início" />
      <input v-model.number="fim" class="input input-bordered w-28" type="number" placeholder="Fim" />
      <input v-model.number="passo" class="input input-bordered w-28" type="number" min="1" placeholder="Passo" />
    </div>
    <button class="btn btn-primary" type="button" @click="contar">Contar</button>
    <p class="font-semibold break-words" aria-live="polite">{{ resultado }}</p>
  </div>
</template>
