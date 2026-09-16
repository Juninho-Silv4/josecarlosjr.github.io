<script setup lang="ts">
import { onUnmounted, ref } from 'vue'

defineOptions({ name: 'ExercicioUm' })

const resultado = ref('Clique no botão para verificar o horário.')
let relogio: ReturnType<typeof setInterval> | undefined

function verificarHorario() {
  const agora = new Date()
  const hora = agora.getHours()
  const horario = agora.toLocaleTimeString('pt-BR', {
    hour: '2-digit',
    minute: '2-digit',
    second: '2-digit',
  })
  const periodo = hora < 12 ? 'Bom dia!' : hora < 18 ? 'Boa tarde!' : 'Boa noite!'
  resultado.value = `Agora são ${horario}.\n${periodo}`

  if (!relogio) {
    relogio = setInterval(verificarHorario, 1000)
  }
}
const txt1 = 'Verificador de horário';
const txt2 = 'Descubra o período do dia de acordo com o horário atual.';
const txt3 = 'Verificar horário';

onUnmounted(() => {
  if (relogio) clearInterval(relogio)
})
</script>

<template>
  <div class="w-full space-y-4 text-center">
    <h1 class="text-2xl font-bold">{{ txt1 }}</h1>
    <p>{{ txt2 }}</p>
    <button class="btn btn-primary" type="button" @click="verificarHorario">{{ txt3 }}</button>
    <p class="whitespace-pre-line font-semibold" aria-live="polite">{{ resultado }}</p>
  </div>
</template>
