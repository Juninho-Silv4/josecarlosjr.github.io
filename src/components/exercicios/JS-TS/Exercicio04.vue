<script setup lang="ts">
import { ref } from 'vue'

defineOptions({ name: 'ExercicioQuatro' })

const numero = ref<number | null>(null)
const tabuada = ref<number[]>([])

function calcularTabuada() {
  if (numero.value === null) {
    tabuada.value = []
    return
  }

  tabuada.value = Array.from({ length: 10 }, (_, indice) => numero.value! * (indice + 1))
}
</script>

<template>
  <div class="w-full space-y-4 text-center">
    <h1 class="text-2xl font-bold">Tabuada</h1>
    <label class="flex flex-col items-center gap-2">
      Digite um número
      <input v-model.number="numero" class="input input-bordered" type="number" />
    </label>
    <button class="btn btn-primary" type="button" @click="calcularTabuada">Calcular</button>
    <ul v-if="tabuada.length" class="mx-auto w-fit text-left" aria-live="polite">
      <li v-for="(resultado, indice) in tabuada" :key="indice">{{ numero }} × {{ indice + 1 }} = {{ resultado }}</li>
    </ul>
  </div>
</template>
