<script setup lang="ts">
import { computed } from "vue";
import AppFooter from "../components/AppFooter.vue";
import BtnProximo from "../components/BtnProximo.vue";
import BtnVoltar from "../components/BtnVoltar.vue";
import Exercicio01 from "../components/exercicios/html-css/Exercicio01.vue";
import Exercicio02 from "../components/exercicios/html-css/Exercicio02.vue";
import Exercicio03 from "../components/exercicios/html-css/Exercicio03.vue";
import Exercicio04 from "../components/exercicios/html-css/Exercicio04.vue";
import Exercicio05 from "../components/exercicios/html-css/Exercicio05.vue";
import Exercicio06 from "../components/exercicios/html-css/Exercicio06.vue";
import Exercicio07 from "../components/exercicios/html-css/Exercicio07.vue";
import Exercicio08 from "../components/exercicios/html-css/Exercicio08.vue";

const props = defineProps<{
  exercicio: string;
}>();

const exercicios = {
  "1": Exercicio01,
  "2": Exercicio02,
  "3": Exercicio03,
  "4": Exercicio04,
  "5": Exercicio05,
  "6": Exercicio06,
  "7": Exercicio07,
  "8": Exercicio08,
};

const componenteExercicio = computed(
  () => exercicios[props.exercicio as keyof typeof exercicios] ?? Exercicio01,
);
</script>

<template>
  <div class="flex min-h-screen items-center justify-center bg-base-100 p-6">
    <div class="flex min-h-[650px] w-full max-w-[900px] flex-col border border-base-300 p-6">
      <div class="flex w-full flex-1 flex-col items-center justify-center gap-4 text-center">
        <component :is="componenteExercicio" />

        <div class="flex gap-4">
          <BtnVoltar />
          <BtnProximo />
        </div>
      </div>
      <AppFooter />
    </div>
  </div>
</template>
