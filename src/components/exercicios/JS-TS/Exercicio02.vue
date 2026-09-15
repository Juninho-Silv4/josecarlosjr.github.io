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
  resultado.value = `Detectamos uma pessoa ${sexo.value} com ${idade} anos.`
}
</script>

<template>
  <div class="w-full space-y-4 text-center">
    <h1 class="text-2xl font-bold">Verificador de idade</h1>
    <label class="flex flex-col items-center gap-2">
      Ano de nascimento
      <input v-model.number="anoNascimento" class="input input-bordered" type="number" min="1900" :max="new Date().getFullYear()" />
    </label>
    <div class="flex justify-center gap-4">
      <label><input v-model="sexo" type="radio" value="masculino" /> Masculino</label>
      <label><input v-model="sexo" type="radio" value="feminino" /> Feminino</label>
      <label><input v-model="sexo" type="radio" value="outra identidade" /> Outro</label>
    </div>
    <button class="btn btn-primary" type="button" @click="verificarIdade">Verificar idade</button>
    <p class="font-semibold" aria-live="polite">{{ resultado }}</p>
  </div>
</template>
