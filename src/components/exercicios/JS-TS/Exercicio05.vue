<script setup lang="ts">
import { computed, ref } from 'vue'

defineOptions({ name: 'ExercicioCinco' })

const entrada = ref<number | null>(null)
const numeros = ref<number[]>([])
const finalizado = ref(false)
const maior = computed(() => Math.max(...numeros.value))
const menor = computed(() => Math.min(...numeros.value))
const soma = computed(() => numeros.value.reduce((total, numero) => total + numero, 0))
const media = computed(() => soma.value / numeros.value.length)

function adicionarNumero() {
  const numeroAtual = entrada.value

  if (
    numeroAtual === null ||
    !Number.isFinite(numeroAtual) ||
    numeroAtual < 1 ||
    numeroAtual > 100
  ) {
    return
  }

  if (numeros.value.includes(numeroAtual)) return
  numeros.value.push(numeroAtual)
  entrada.value = null
  finalizado.value = false
}

function finalizar() {
  finalizado.value = numeros.value.length > 0
}

const txt1 = 'Analisador de números'
const txt2 = 'Adicione números válidos e veja um resumo da sequência.'
const txt3 = 'Adicionar'
const txt4 = 'Números: '
const txt5 = 'Finalizar'
const txt6 = 'Ao todo, foram'
const txt7 = 'números.'
const txt8 = 'Maior valor:'
const txt9 = 'Menor valor:'
const txt10 = 'Soma:'
const txt11 = 'Média:'
</script>

<template>
  <div class="w-full space-y-4 text-center">
    <h1 class="text-2xl font-bold">{{ txt1 }}</h1>
    <p>{{ txt2 }}</p>
    <form class="flex justify-center gap-3" @submit.prevent="adicionarNumero">
      <label class="sr-only" for="entrada">Número</label>
      <input
        id="entrada"
        v-model.number="entrada"
        class="input input-bordered w-32"
        type="number"
        min="1"
        max="100"
        placeholder="Número"
      />
      <button class="btn btn-primary" type="submit">{{ txt3 }}</button>
    </form>
    <p v-if="numeros.length">{{ txt4 }}{{ numeros.join(', ') }}</p>
    <button class="btn btn-secondary" type="button" :disabled="!numeros.length" @click="finalizar">{{ txt5 }}</button>
    <div v-if="finalizado" class="space-y-1" aria-live="polite">
      <p>{{ txt6 }} {{ numeros.length }} {{ txt7 }}</p>
      <p>{{ txt8 }} {{ maior }} | {{ txt9 }} {{ menor }}</p>
      <p>{{ txt10 }} {{ soma }} | {{ txt11 }} {{ media.toFixed(2) }}</p>
    </div>
  </div>
</template>
