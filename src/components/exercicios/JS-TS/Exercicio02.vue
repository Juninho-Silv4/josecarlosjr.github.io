<script setup lang="ts">
import { ref } from 'vue'

defineOptions({ name: 'ExercicioDois' })

const anoNascimento = ref<number | null>(null)
const sexo = ref('')
const resultado = ref('Preencha os dados para descobrir a idade.')

function verificarIdade() {
  const anoAtual = new Date().getFullYear()

  if (!anoNascimento.value || anoNascimento.value < 1900 || anoNascimento.value > anoAtual) {
    resultado.value = 'Informe um ano de nascimento válido.'
    return
  }

  if (!sexo.value) {
    resultado.value = 'Selecione uma opção de sexo.'
    return
  }

  const idade = anoAtual - anoNascimento.value
  resultado.value = `Você se identifica como ${sexo.value} e tem ${idade} anos.`
}

const txt1 = 'Verificador de idade'
const txt2 = 'Ano de nascimento'
const txt3 = 'Identidade de gênero'
const txt5 = 'Homem Cis'
const txt6 = 'Mulher Cis'
const txt7 = 'Homem Trans'
const txt8 = 'Mulher Trans'
const txt9 = 'Outro'
const txt10 = 'Verificar idade'
</script>

<template>
  <div class="w-full space-y-4 text-center">
    <h1 class="text-2xl font-bold">{{ txt1 }}</h1>
    <label class="flex flex-col items-center gap-2">
      {{ txt2 }}
      <input v-model.number="anoNascimento" class="input input-bordered" type="number" min="1900" :max="new Date().getFullYear()" />
    </label>
    <h1 class="text-2xl font-bold">{{ txt3 }}</h1>
    <div class="flex justify-center gap-4">
      <label><input v-model="sexo" type="radio" value="homem cis" /> {{ txt5 }}</label>
      <label><input v-model="sexo" type="radio" value="mulher cis" /> {{ txt6 }}</label>
      <label><input v-model="sexo" type="radio" value="homem trans" /> {{ txt7 }}</label>
      <label><input v-model="sexo" type="radio" value="mulher trans" /> {{ txt8 }}</label>
      <label><input v-model="sexo" type="radio" value="outra identidade de gênero" /> {{ txt9 }}</label>
    </div>
    <button class="btn btn-primary" type="button" @click="verificarIdade">{{ txt10 }}</button>
    <p class="font-semibold" aria-live="polite">{{ resultado }}</p>
  </div>
</template>
