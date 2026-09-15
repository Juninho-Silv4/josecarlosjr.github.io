<script setup lang="ts">
import { ref } from 'vue'

defineOptions({ name: 'ExercicioUm' })

const resultado = ref('Clique no botão para verificar o horário.')

function verificarHorario() {
  const hora = new Date().getHours()
  const periodo = hora < 12 ? 'bom dia' : hora < 18 ? 'boa tarde' : 'boa noite'
  resultado.value = `Agora são ${hora} horas. ${periodo}!`
}
</script>

<template>
  <div class="w-full space-y-4 text-center">
    <h1 class="text-2xl font-bold">Verificador de horário</h1>
    <p>Descubra o período do dia de acordo com o horário atual.</p>
    <button class="btn btn-primary" type="button" @click="verificarHorario">Verificar horário</button>
    <p class="font-semibold" aria-live="polite">{{ resultado }}</p>
  </div>
</template>
