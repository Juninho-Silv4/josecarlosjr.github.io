<script setup lang="ts">
  import { onMounted, onUnmounted, ref } from "vue";
  import fotoPerfil from '@/assets/EuEMEJ24.png';
  import fotoPerfil2 from '@/assets/EuandBacon_EMEJ24.png';
  import imgConstrucao from '@/assets/Underconstruction.png';
  import SubmenuPanel from '@/components/SubmenuPanel.vue';

  const nome = "José Carlos Brás da Silva Júnior";
  const menu = ["Fundamentos", "Projetos", "Destques"];
  const submenu1 = ["HTML/CSS", "JavaScript / TypeScript"];
  const submenu2 = ["Disciplinas", "Laboratórios"];
  const submenu3 = ["Em breve",];
  const imgPrincipal = [
    {
      src: fotoPerfil,
      alt: 'Foto de perfil do José Carlos Jr',
    },
    {
      src: fotoPerfil2,
      alt: 'Foto de perfil do José Carlos Jr com Bacon',
    }
  ];

  const imagemPrincipalAtiva = ref(0);
  let carouselTimer: ReturnType<typeof setInterval> | undefined;

  onMounted(() => {
    carouselTimer = setInterval(() => {
      imagemPrincipalAtiva.value = (imagemPrincipalAtiva.value + 1) % imgPrincipal.length;
    }, 2000);
  });

  onUnmounted(() => {
    if (carouselTimer) {
      clearInterval(carouselTimer);
    }
  });
  const exerciciosHtmlCss = [
    "Exercício 1: Meu primeiro exercício!",
    "Exercício 2: Parágrafos e quebra de linha!",
    "Exercício 3: Testando imagens e favicon!",
    "Exercício 4: Formatação de textos e hierarquia de titulos!",
    "Exercício 5: Listas!",
    "Exercício 6: Trabalhando com links!",
    "Exercício 7: Mídias em HTML!",
    "Exercício 8: Estilos!",
  ];

  const exerciciosJsTs = [
    "Exercício 1: Verificador de horário!",
    "Exercício 2: Vereficador de idade!",
    "Exercício 3: Contador!",
    "Exercício 4: Tabuada!",
    "Exercício 5: Analisador de números!",
  ];

  const disciplinas = [
    "Programação Orientada a Objetos",
    "Programação Funcional",
  ];

  const labs = [
    "App de checklist",
  ];

  const emBreve = [
    "Novos projetos em desenvolvimento",
  ];

  const secoesSubmenu1 = [
    exerciciosHtmlCss.map((label, index) => ({
      label,
      to: { name: 'html-css-exercicio', params: { exercicio: String(index + 1) } },
    })),
    exerciciosJsTs.map((label, index) => ({
      label,
      to: { name: 'js-ts-exercicio', params: { exercicio: String(index + 1) } },
    })),
  ];
  const secoesSubmenu2 = [
    disciplinas.map((label) => ({ label })),
    labs.map((label) => ({ label })),
  ];
  const secoesSubmenu3 = [
    emBreve.map((label) => ({ label })),
  ];
  const imagensSubmenu1 = [
    [
      { src: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg", alt: "Logo HTML" },
      { src: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg", alt: "Logo CSS" },
    ],
    [
      { src: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg", alt: "Logo JavaScript" },
      { src: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg", alt: "Logo TypeScript" },
    ],
  ];
  const imagensSubmenu2 = [
    [{ src: imgConstrucao, alt: "Ilustração de disciplinas" }],
    [{ src: imgConstrucao, alt: "Ilustração de laboratórios" }],
  ];
  const imagensSubmenu3 = [[{ src: imgConstrucao, alt: "Ilustração de tecnologias" }],];

  const txtspan = "Fotos do EMEJ24 - Encontro Mineiro de Empresas Juniores de 2024!";

</script>

<template>
  <div class="flex min-h-screen items-center justify-center bg-base-100 p-6">
    <div class="home-card w-full max-w-[900px] min-h-[650px] rounded-2xl border-2 border-black p-6 shadow-[0_16px_40px_rgba(0,0,0,0.25)] backdrop-blur-sm">
      <div class="mb-6 flex items-center justify-center gap-4 text-center">
        <div class="group relative h-40 w-25 shrink-0 overflow-hidden rounded-lg border border-base-content/40" tabindex="0">
          <img
            v-for="(imagem, index) in imgPrincipal"
            :key="imagem.src"
            :src="imagem.src"
            class="absolute inset-0 h-full w-full object-cover transition-opacity duration-500"
            :class="index === imagemPrincipalAtiva ? 'opacity-100' : 'opacity-0'"
            :alt="imagem.alt"
          />
          <span class="pointer-events-none absolute inset-x-0 bottom-0 z-10 bg-black/60 px-2 py-1 text-xs leading-tight text-white opacity-0 transition-opacity duration-300 group-hover:opacity-100 group-focus:opacity-100">
            {{ txtspan }}
          </span>
        </div>
        <p class="text-base font-semibold tracking-wide text-base-content">
          {{ nome }}
        </p>
      </div>

      <button class="btn sm:hidden" popovertarget="my-megamenu-3">Menu</button>
      <div
        class="megamenu max-sm:megamenu-vertical megamenu-wide mx-auto w-full max-w-[720px] border border-base-300 bg-base-100/70 p-2"
        id="my-megamenu-3"
        popover
      >
        <div class="flex w-full items-center justify-between gap-4 px-10">
          <button class="btn flex-1 items-center justify-center border border-base-300 bg-base-100 text-center text-sm font-medium transition hover:bg-base-200" popovertarget="c1">
            {{ menu[0] }}
          </button>
          <button class="btn flex-1 items-center justify-center border border-base-300 bg-base-100 text-center text-sm font-medium transition hover:bg-base-200" popovertarget="c2">
            {{ menu[1] }}
          </button>
          <button class="btn flex-1 items-center justify-center border border-base-300 bg-base-100 text-center text-sm font-medium transition hover:bg-base-200" popovertarget="c3">
            {{ menu[2] }}
          </button>
        </div>

        <div id="c1" popover>
          <SubmenuPanel
            :tabs="submenu1"
            :sections="secoesSubmenu1"
            :images="imagensSubmenu1"
          />
        </div>

        <div id="c2" popover>
          <SubmenuPanel
            :tabs="submenu2"
            :sections="secoesSubmenu2"
            :images="imagensSubmenu2"
          />
        </div>

        <div id="c3" popover>
          <SubmenuPanel
            :tabs="submenu3"
            :sections="secoesSubmenu3"
            :images="imagensSubmenu3"
          />
        </div>
      </div>
    </div>
  </div>
</template>
