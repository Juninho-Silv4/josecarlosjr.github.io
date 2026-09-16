<script setup lang="ts">
  defineOptions({
    name: 'ExercicioSeis',
  })

  const baseUrl = import.meta.env.BASE_URL;
  const txt1 = 'Usando links externos';
  const txt2 = 'Você pode acessar o meu';
  const txt3 = 'repositório público no GitHub';
  const txt4 = 'Você também pode acessar o';
  const txt5 = 'YouTube';
  const txt6 = 'gratuitamente!';
  const txt7 = 'Usando links internos';
  const txt8 = 'Esta é a primeira página do site. A navegação entre exercícios é feita pelos botões abaixo.';
  const txt8Span = 'Nessa etapa o site ainda não estava pronto, então a navegação entre exercícios não funcionava. Foi construido a partir desse ponto nas video aulas do curso de HTML e CSS do professor Gustavo Guanabara';
  const txt9 = 'Links para download';
  const txt10 = 'Baixar o PDF';

  const externalLinks = [
    {
      label: txt3,
      href: 'https://github.com/Juninho-Silv4',
    },
    {
      label: txt5,
      href: 'https://www.youtube.com/',
    },
  ];

  const downloadLinks = [
    {
      label: txt9,
      fileName: 'JOSECBSJUNIOR.pdf',
      type: 'application/pdf',
    },
  ];
</script>

<template>
  <div class="w-full space-y-4 text-center">
    <h1 class="text-2xl font-bold">{{ txt1 }}</h1>

    <p v-for="(link, index) in externalLinks" :key="link.href">
      {{ index === 0 ? txt2 : txt4 }}
      <a
        class="link link-primary"
        :href="link.href"
        target="_blank"
        rel="noopener noreferrer"
      >
        {{ link.label }}
      </a>.
      {{ txt6 }}
    </p>

    <h2 class="text-2xl font-bold">{{ txt7 }}</h2>
    <p class="group relative mx-auto w-fit">
      <span
        class="cursor-help"
        tabindex="0"
        aria-describedby="navigation-description"
      >
        {{ txt8 }}
      </span>
      <span
        id="navigation-description"
        role="tooltip"
        class="invisible absolute left-1/2 top-full z-10 mt-2 w-72 -translate-x-1/2 rounded-box bg-base-300 p-3 text-sm font-normal text-base-content opacity-0 shadow-lg transition-opacity group-hover:visible group-hover:opacity-100 group-focus-within:visible group-focus-within:opacity-100"
      >
        {{ txt8Span }}
      </span>
    </p>

    <h2 class="text-2xl font-bold">{{ txt9   }}</h2>
    <ul class="list-disc pl-6">
      <li v-for="link in downloadLinks" :key="link.fileName">
        <a
          class="link link-primary"
          :href="`${baseUrl}exercises/html-css/ex06/${link.fileName}`"
          :download="link.fileName"
          :type="link.type"
        >
          {{ link.type === 'application/pdf' ? txt10 : link.label }}
        </a>
      </li>
    </ul>
  </div>
</template>
