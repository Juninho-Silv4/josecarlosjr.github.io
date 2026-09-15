<script setup lang="ts">
  import { computed, ref } from "vue";


  const nome = "José Carlos Brás da Silva Júnior";
  const menu = ["Fundamentos", "Projetos", "Destques"];
  const submenu1 = ["HTML/CSS", "JavaScript / TypeScript", "Tailwind CSS", "Vue.js"];
  const submenuAtivo = ref<0 | 1>(0);
  const imgPrincipal = [
    {
      src: "https://media.licdn.com/dms/image/v2/D4D03AQHBuThf8gkfKg/profile-displayphoto-shrink_100_100/B4DZWxrxOrH4AU-/0/1742442796803?e=1789603200&v=beta&t=ZP_ux6M5KnFu-bTsR6vsu5hvtQyUg1pgE3S4tEnYNh0",
      alt: "Foto de perfil do José Carlos Jr",
    },
  ]
  const imagSubmenu = [
    [
      {
        src: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg",
        alt: "Logo HTML",
      },
      {
        src: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg",
        alt: "Logo CSS",
      },
    ],
    [
      {
        src: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg",
        alt: "Logo JavaScript",
      },
      {
        src: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg",
        alt: "Logo TypeScript",
      },
    ],
  ];
  const imgSubmenuAtiva = computed(() => imagSubmenu[submenuAtivo.value] ?? imagSubmenu[0]!);
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

</script>

<template>
  <div class="flex min-h-screen items-center justify-center bg-base-100 p-6">
    <div class="home-card w-full max-w-[900px] min-h-[650px] rounded-2xl border-2 border-black p-6 shadow-[0_16px_40px_rgba(0,0,0,0.25)] backdrop-blur-sm">
      <div class="mb-6 flex items-center justify-center gap-4 text-center">
        <img
          v-for="imagem in imgPrincipal"
          :key="imagem.src"
          :src="imagem.src"
          class="shrink-0 rounded-full object-cover"
          :alt="imagem.alt"
        />
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
        <span class="megamenu-active"></span>

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
          <div class="grid w-full md:grid-cols-2">
            <div class="w-full">
              <ul class="menu w-full flex-row flex-nowrap md:menu-horizontal">
                <li>
                  <a class="justify-center text-center" @click="submenuAtivo = 0">
                    {{ submenu1[0]}}
                  </a>
                </li>
                <li>
                  <a class="justify-center text-center" @click="submenuAtivo = 1">
                    {{ submenu1[1]}}
                  </a>
                </li>
              </ul>

              <ul v-if="submenuAtivo === 0" class="menu flex-col">
                <li v-for="(exercicio, index) in exerciciosHtmlCss" :key="exercicio">
                  <RouterLink :to="{ name: 'html-css-exercicio', params: { exercicio: String(index + 1) } }">
                    {{ exercicio }}
                  </RouterLink>
                </li>
              </ul>
              <ul v-else class="menu flex-col">
                <li v-for="(exercicio, index) in exerciciosJsTs" :key="exercicio">
                  <RouterLink :to="{ name: 'js-ts-exercicio', params: { exercicio: String(index + 1) } }">
                    {{ exercicio }}
                  </RouterLink>
                </li>
              </ul>
            </div>
            <div class="flex w-1.5/5 items-center justify-center gap-2">
              <img
                v-for="imagem in imgSubmenuAtiva"
                :key="imagem.src"
                :src="imagem.src"
                class="h-20 w-20 shrink-0 object-contain"
                :alt="imagem.alt"
              />
            </div>
          </div>
        </div>

        <div id="c2" popover>
          <div class="flex max-sm:flex-col items-start">
            <ul class="menu w-full md:menu-horizontal">
              <li>
                <a>
                  {{"algo" }}
                </a>
                <ul>
                  <li><a>CRM software</a></li>
                  <li><a>Marketing management</a></li>
                  <li><a>Security</a></li>
                  <li><a>Consulting</a></li>
                  <li><a>Privacy policy</a></li>
                  <li><a>Press kit</a></li>
                </ul>
              </li>
            </ul>
            <img
              src="https://freesvg.org/img/1486640958.png"
              class="md:max-w-sm max-md:w-auto"
              alt="Tailwind CSS megamenu component"
            />
          </div>
        </div>

        <div id="c3" popover>
          <div class="flex max-sm:flex-col items-start">
            <ul class="menu w-full md:menu-horizontal">
              <li>
                <ul>
                  <li class="menu-title">
                    {{ submenu1[2] + " & " + submenu1[3] }}
                  </li>
                  <li><a>Design</a></li>
                  <li><a>Development</a></li>
                  <li><a>Hosting</a></li>
                  <li><a>Domain register</a></li>
                </ul>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
