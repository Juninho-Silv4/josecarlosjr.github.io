<script setup lang="ts">
</script>

<template>
  <div class="flex items-center justify-center min-h-screen p-6">
    <button class="btn sm:hidden" popovertarget="my-megamenu-3">Menu</button>
    <div
      class="megamenu max-sm:megamenu-vertical megamenu-wide p-2 border border-base-600 min-w-[420px] w-full max-w-[720px]"
      id="my-megamenu-3"
      popover
    >
      <span class="megamenu-active"></span>

      <div class="flex w-full items-center justify-between gap-4 px-10">
        <button class="btn flex-1 items-center justify-center text-center" popovertarget="c1">Fundamentos</button>
        <button class="btn flex-1 items-center justify-center text-center" popovertarget="c2">Projetos</button>
        <button class="btn flex-1 items-center justify-center text-center" popovertarget="c3">Destques</button>
      </div>

      <div id="c1" popover>
        <div class="flex max-sm:flex-col items-start">
          <ul class="menu w-full md:menu-horizontal">
            <li>
              <a>HTML/CSS</a>
              <ul>
                <li><a>CRM software</a></li>
                <li><a>Marketing management</a></li>
                <li><a>Security</a></li>
                <li><a>Consulting</a></li>
              </ul>
            </li>
          </ul>
          <img
            src="https://png.pngtree.com/png-clipart/20230609/ourmid/pngtree-logo-html-css-icone-and-png-image_7123436.png"
            class="md:max-w-sm max-md:w-auto"
            alt="Tailwind CSS megamenu"
          />
        </div>
      </div>

      <div id="c2" popover>
        <div class="flex max-sm:flex-col items-start">
          <ul class="menu w-full md:menu-horizontal">
            <li>
              <a>JavaScript / TypeScript</a>
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
                <li class="menu-title">Solutions</li>
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
</template>
