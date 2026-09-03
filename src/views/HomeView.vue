<script setup lang="ts">
  import { computed, ref } from "vue";

  const nome = "José Carlos Brás da Silva Júnior";
  const menu = ["Fundamentos", "Projetos", "Destques"];
  const submenu1 = ["HTML/CSS", "JavaScript / TypeScript", "Tailwind CSS", "Vue.js"];
  const submenuAtivo = ref<0 | 1>(0);
  const imagensSubmenu = [
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
  const imagemSubmenuAtiva = computed(() => imagensSubmenu[submenuAtivo.value] ?? imagensSubmenu[0]!);
  const menuFund =
  ["Exercício 1: Meu primeiro exercício!",
    "Exercício 2: Parágrafos e quebra de linha!",
    "Exercício 3: Testando imagens e favicon!",
    "Exercício 4: Formatação de textos e hierarquia de titulos!",
    "Exercício 5: Listas!",
    "Exercício 6: Trabalhando com links!",
    "Exercício 7: Mídias em HTML!",
    "Exercício 8: Estilos!",
    "Exercício 1: Verificador de horário!",
    "Exercício 2: Vereficador de idade!",
    "Exercício 3: Contador!",
    "Exercício 4: Tabuada!",
    "Exercício 5: Analisador de números!",
  ];


</script>

<template>
  <div class="flex min-h-screen items-center justify-center bg-base-100 p-6">
    <div class="w-full max-w-[900px] rounded-2xl border border-base-300 bg-base-200/80 p-6 shadow-[0_12px_30px_rgba(0,0,0,0.08)] backdrop-blur-sm">
      <div class="mb-6 flex items-center justify-center gap-4 text-center">
        <img
          src="https://media.licdn.com/dms/image/v2/D4D03AQHBuThf8gkfKg/profile-displayphoto-shrink_100_100/B4DZWxrxOrH4AU-/0/1742442796803?e=1789603200&v=beta&t=ZP_ux6M5KnFu-bTsR6vsu5hvtQyUg1pgE3S4tEnYNh0"
          class="h-24 w-24 rounded-full border-2 border-base-300 object-cover shadow-md"
          alt="José Carlos Jr"
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
          <div class="grid w-full gap-4 md:grid-cols-[minmax(0,1fr)_11rem]">
            <div class="min-w-0">
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

              <ul v-if="submenuAtivo === 0" class="menu w-4/5 flex-col">
                <li><a>{{menuFund[0]}}</a></li>
                <li><a>{{menuFund[1]}}</a></li>
                <li><a>{{menuFund[2]}}</a></li>
                <li><a>{{menuFund[3]}}</a></li>
                <li><a>{{menuFund[4]}}</a></li>
                <li><a>{{menuFund[5]}}</a></li>
                <li><a>{{menuFund[6]}}</a></li>
                <li><a>{{menuFund[7]}}</a></li>
              </ul>
              <ul v-else class="menu w-4/5 flex-col">
                <li><a>{{menuFund[8]}}</a></li>
                <li><a>{{menuFund[9]}}</a></li>
                <li><a>{{menuFund[10]}}</a></li>
                <li><a>{{menuFund[11]}}</a></li>
                <li><a>{{menuFund[12]}}</a></li>
              </ul>
            </div>
            <div class="flex items-start justify-center gap-2 pt-12">
              <img
                v-for="imagem in imagemSubmenuAtiva"
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
