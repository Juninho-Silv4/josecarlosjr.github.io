<script setup lang="ts">
import { computed } from "vue";
import { useRoute, useRouter } from "vue-router";

const route = useRoute();
const router = useRouter();
const totalExercicios = 8;

const exercicioAtual = computed(() => Number(route.params.exercicio));

function goNext() {
  const proximoExercicio = (exercicioAtual.value % totalExercicios) + 1;

  router.push({
    name: "html-css-exercicio",
    params: { exercicio: String(proximoExercicio) },
  });
}
</script>

<template>
  <button
    class="btn border border-base-300 bg-base-100 text-center text-sm font-medium transition hover:bg-base-200"
    @click="goNext"
  >
    Próximo
  </button>
</template>
