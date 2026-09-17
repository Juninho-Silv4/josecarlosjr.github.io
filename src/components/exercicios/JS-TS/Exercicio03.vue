<script setup lang="ts">
  import { ref } from 'vue'

  defineOptions({
    name: 'ExercicioTres',
  })

  const inicio = ref < number | null > (null)
  const fim = ref < number | null > (null)
  const passo = ref < number | null > (null)
  const valores = ref < number[] > ([])
  const mensagem = ref < string > ('Informe início, fim e passo para contar.')

  function contar() {
    const inicioAtual = inicio.value
    const fimAtual = fim.value
    const passoAtual = passo.value

    if (
      inicioAtual === null ||
      fimAtual === null ||
      passoAtual === null ||
      !Number.isFinite(inicioAtual) ||
      !Number.isFinite(fimAtual) ||
      !Number.isFinite(passoAtual) ||
      passoAtual <= 0
    ) {
      valores.value = []
      mensagem.value = 'Preencha os campos com valores válidos.'
      return
    }

    valores.value = []

    const direcao = inicioAtual <= fimAtual ? 1 : -1

    for (
      let valor = inicioAtual;
      direcao === 1 ? valor <= fimAtual : valor >= fimAtual;
      valor += passoAtual * direcao
    ) {
      valores.value.push(valor)
    }

    mensagem.value = ''
  }

  const txt1 = 'Contador'
  const txt2 = 'Início'
  const txt3 = 'Fim'
  const txt4 = 'Passo'
</script>

<template>
  <div class="w-full space-y-4 text-center">
    <h1 class="text-2xl font-bold">{{ txt1 }}</h1>

    <form class="space-y-4" @submit.prevent="contar">
      <div class="flex flex-wrap justify-center gap-3">
        <label>
          {{ txt2 }}
          <input
            v-model.number="inicio"
            class="input input-bordered w-28"
            type="number"
          />
        </label>

        <label>
          {{ txt3 }}
          <input
            v-model.number="fim"
            class="input input-bordered w-28"
            type="number"
          />
        </label>

        <label>
          {{ txt4 }}
          <input
            v-model.number="passo"
            class="input input-bordered w-28"
            type="number"
            min="1"
          />
        </label>
      </div>

      <button class="btn btn-primary" type="submit">Contar</button>
    </form>

    <p v-if="mensagem" class="font-semibold" aria-live="polite">
      {{ mensagem }}
    </p>
    <p
      v-else
      class="flex flex-wrap justify-center gap-2 font-semibold"
      aria-live="polite"
    >
      <template v-for="(valor, indice) in valores" :key="`${valor}-${indice}`">
        <span>{{ valor }}</span>
        <span v-if="indice < valores.length - 1" aria-hidden="true">→</span>
      </template>
    </p>
  </div>
</template>
