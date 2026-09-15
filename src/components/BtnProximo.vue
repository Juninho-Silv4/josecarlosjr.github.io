<script setup lang="ts">
import { computed } from "vue";
import { useRoute, useRouter } from "vue-router";

const route = useRoute();
const router = useRouter();

const configuracaoExercicios = computed(() => {
  if (route.name === "js-ts-exercicio") {
    return {
      total: 5,
      rota: "js-ts-exercicio",
    };
  }

  return {
    total: 8,
    rota: "html-css-exercicio",
  };
});

const exercicioAtual = computed(() => Number(route.params.exercicio));

function goNext() {
  const proximoExercicio =
    (exercicioAtual.value % configuracaoExercicios.value.total) + 1;

  router.push({
    name: configuracaoExercicios.value.rota,
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
