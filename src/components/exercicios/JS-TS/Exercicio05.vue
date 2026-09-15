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
  if (entrada.value === null || entrada.value < 1 || entrada.value > 100) return
  if (numeros.value.includes(entrada.value)) return
  numeros.value.push(entrada.value)
  entrada.value = null
  finalizado.value = false
}

function finalizar() {
  finalizado.value = numeros.value.length > 0
}
</script>

<template>
  <div class="w-full space-y-4 text-center">
    <h1 class="text-2xl font-bold">Analisador de números</h1>
    <p>Adicione números entre 1 e 100 e veja um resumo da sequência.</p>
    <div class="flex justify-center gap-3">
      <input v-model.number="entrada" class="input input-bordered w-32" type="number" min="1" max="100" placeholder="Número" />
      <button class="btn btn-primary" type="button" @click="adicionarNumero">Adicionar</button>
    </div>
    <p v-if="numeros.length">Números: {{ numeros.join(', ') }}</p>
    <button class="btn btn-secondary" type="button" :disabled="!numeros.length" @click="finalizar">Finalizar</button>
    <div v-if="finalizado" class="space-y-1" aria-live="polite">
      <p>Ao todo, foram {{ numeros.length }} números.</p>
      <p>Maior valor: {{ maior }} | Menor valor: {{ menor }}</p>
      <p>Soma: {{ soma }} | Média: {{ media.toFixed(2) }}</p>
    </div>
  </div>
</template>
