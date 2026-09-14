<script setup lang="ts">
import { useRouter } from "vue-router";

const router = useRouter();

function goBack() {
  router.push("/");
}
</script>

<template>
  <button
    class="btn border border-base-300 bg-base-100 text-center text-sm font-medium transition hover:bg-base-200"
    @click="goBack"
  >
    Voltar
  </button>
</template>
