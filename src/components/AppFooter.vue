<script setup lang="ts">
  import { useRouter } from "vue-router";

  const router = useRouter();
  const linkedinUrl = "https://www.linkedin.com/in/jose-carlos-bras-da-silva-junior-004828214/";

  function gotoPage(url: string) {
    router.push(url);
  }
</script>

<template>
  <footer class="mt-6 shrink-0 text-center text-sm text-base-content">
    © Desenvolvido por
    <strong @click="gotoPage(linkedinUrl)">José Carlos (Juninho)</strong>, 2023.
  </footer>
</template>
