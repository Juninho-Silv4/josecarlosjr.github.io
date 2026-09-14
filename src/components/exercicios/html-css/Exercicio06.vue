<template>
  <div class="w-full space-y-4 text-center">
    <h1 class="text-2xl font-bold">Usando links externos</h1>

    <p>
      Você pode acessar o meu
      <a class="link link-primary" href="https://github.com/" target="_blank" rel="external">
        repositório público no GitHub
      </a>.
    </p>
    <p>
      Você também pode acessar o meu
      <a class="link link-primary" href="https://www.youtube.com/" target="_blank" rel="external">
        canal gratuito no YouTube
      </a>.
    </p>

    <h1 class="text-2xl font-bold">Usando links internos</h1>
    <p>Esta é a primeira página do site. A navegação entre exercícios é feita pelos botões abaixo.</p>

    <h1 class="text-2xl font-bold">Links para download</h1>
    <ul class="list-disc pl-6">
      <li>
        <a
          class="link link-primary"
          href="/exercises/html-css/ex06/ATESTADO_MATRICULA__GRADUACAO2024197.pdf"
          download="ATESTADO_MATRICULA__GRADUACAO2024197.pdf"
          type="application/pdf"
        >
          Baixar o PDF
        </a>
      </li>
      <li>
        <a
          class="link link-primary"
          href="/exercises/html-css/ex06/ATESTADO_MATRICULA__GRADUACAO2024197.pdf"
          download="meulivro.zip"
          type="application/zip"
        >
          Livro compactado em ZIP
        </a>
      </li>
    </ul>
  </div>
</template>
