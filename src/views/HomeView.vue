<script setup lang="ts">
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
        <p class="text-base font-semibold tracking-wide text-base-content">José Carlos Brás da Silva Júnior</p>
      </div>

      <button class="btn sm:hidden" popovertarget="my-megamenu-3">Menu</button>
      <div
        class="megamenu max-sm:megamenu-vertical megamenu-wide mx-auto w-full max-w-[720px] border border-base-300 bg-base-100/70 p-2"
        id="my-megamenu-3"
        popover
      >
        <span class="megamenu-active"></span>

        <div class="flex w-full items-center justify-between gap-4 px-10">
          <button class="btn flex-1 items-center justify-center border border-base-300 bg-base-100 text-center text-sm font-medium transition hover:bg-base-200" popovertarget="c1">Fundamentos</button>
          <button class="btn flex-1 items-center justify-center border border-base-300 bg-base-100 text-center text-sm font-medium transition hover:bg-base-200" popovertarget="c2">Projetos</button>
          <button class="btn flex-1 items-center justify-center border border-base-300 bg-base-100 text-center text-sm font-medium transition hover:bg-base-200" popovertarget="c3">Destques</button>
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
  </div>
</template>
