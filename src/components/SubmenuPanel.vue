<script setup lang="ts">
  import { ref } from "vue";
  import type { RouteLocationRaw } from "vue-router";

  type SubmenuItem = {
    label: string;
    to?: RouteLocationRaw;
  };

  type SubmenuImage = {
    src: string;
    alt: string;
  };

  const props = defineProps<{
    tabs: string[];
    sections: SubmenuItem[][];
    images: SubmenuImage[][];
  }>();

  const activeTab = ref(0);
</script>

<template>
  <div class="grid w-full md:grid-cols-2">
    <div class="w-full">
      <ul class="menu w-full flex-row flex-nowrap md:menu-horizontal">
        <li v-for="(tab, index) in props.tabs" :key="tab">
          <a class="justify-center text-center" @click="activeTab = index">
            {{ tab }}
          </a>
        </li>
      </ul>

      <ul class="menu flex-col">
        <li v-for="item in props.sections[activeTab]" :key="item.label">
          <RouterLink v-if="item.to" :to="item.to">
            {{ item.label }}
          </RouterLink>
          <a v-else>{{ item.label }}</a>
        </li>
      </ul>
    </div>

    <div class="flex items-center justify-center gap-2">
      <img
        v-for="image in props.images[activeTab]"
        :key="image.src"
        :src="image.src"
        class="h-20 w-20 shrink-0 object-contain"
        :alt="image.alt"
      />
    </div>
  </div>
</template>
