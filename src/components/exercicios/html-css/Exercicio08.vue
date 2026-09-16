<script setup lang="ts">
  defineOptions({
    name: 'ExercicioOito',
  })

  const txt1 = 'Capítulo 1';
  const txt2 = 'Capítulo 1.1';
  const txt3 = 'Capítulo 1.2';
  const txt4 = 'Capítulo 2';
  const txt5 = 'Capítulo 2.1';

  const parag1 = 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut hendrerit, diam eu mattis finibus, est felis pretium ipsum, eget ullamcorper arcu nisi in dui. Morbi finibus, dui eget hendrerit egestas, diam quam sodales lacus, vel lacinia nulla enim sed ligula. Maecenas elementum vulputate quam, sit amet placerat turpis dapibus sit amet. Sed egestas fermentum arcu dapibus porta. Etiam dictum dui et sapien tincidunt, sit amet finibus dolor viverra. Curabitur feugiat ac dui ac elementum. Aenean in vestibulum lacus, nec congue ante. In hac habitasse platea dictumst. Nam pretium nunc enim, id ullamcorper erat aliquam id.';
  const parag2 = 'Etiam congue scelerisque mollis. Quisque ac dignissim justo. Cras varius convallis elit, in consectetur lacus auctor id. Praesent rhoncus, magna et elementum volutpat, libero nisl venenatis tellus, a venenatis ipsum quam id neque. Sed dapibus velit sapien, vel pretium elit tempus sed. Duis augue velit, volutpat in turpis vel, pretium placerat ipsum. Cras finibus fermentum magna ut porttitor. Aliquam elit urna, egestas vitae ultrices et, pellentesque commodo tellus. Nunc pulvinar quam vel risus euismod, eu scelerisque ante commodo. Interdum et malesuada fames ac ante ipsum primis in faucibus. Sed et aliquet augue.';
  const parag3 = 'Nam ante nulla, consequat sed varius et, aliquet vel orci. Integer ac dolor tortor. Donec dapibus faucibus diam sit amet finibus. Quisque rutrum ligula at finibus elementum. Proin facilisis faucibus enim vitae tincidunt. Vestibulum porta pellentesque aliquam. Vivamus ac tincidunt diam, ut consequat quam. Sed lacinia, lorem id dictum laoreet, risus ipsum facilisis nunc, vel efficitur massa quam non lacus. Vivamus porta viverra ultricies. Vivamus eu tellus dignissim, ornare erat efficitur, semper ligula. Pellentesque tempor libero eu lacinia elementum. Cras pellentesque lacus faucibus arcu iaculis dictum. Donec congue commodo aliquet. Aenean ac metus nisi. Sed condimentum rhoncus sem, sit amet feugiat mi maximus id.';
</script>

<template>
  <div
    class="w-full space-y-4 text-center font-sans"
    style="background-color: blueviolet; padding: 1rem;"
  >
    <h1 class="text-[50px]" style="color: midnightblue;">{{ txt1 }}</h1>
    <h2 class="text-[30px]" style="color: magenta;">{{ txt2 }}</h2>
    <p class="text-justify">
      {{ parag1 }}
    </p>

    <h2 class="text-[30px]" style="color: magenta;">{{ txt3 }}</h2>
    <p class="text-justify">
      {{ parag2 }}
    </p>

    <h1 class="text-[50px]" style="color: midnightblue;">{{ txt4 }}</h1>
    <h2 class="text-[30px]" style="color: magenta;">{{ txt5 }}</h2>
    <p class="text-justify">
      {{ parag3 }}
    </p>

    <h1 class="text-[50px]" style="color: midnightblue;">{{ txt4 }}</h1>
    <h2 class="text-[30px]" style="color: magenta;">{{ txt5 }}</h2>
    <p class="text-justify">
      {{ parag3 }}
    </p>

    <code class="block text-center">
      style="color: midnightblue;"<br />
      style="color: magenta;"<br />
      style="text-align: justify;"<br />
      /* Normalmente usado na declaração do parâmetro HTML! */
    </code>
  </div>
</template>
