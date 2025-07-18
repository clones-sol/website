<script lang="ts">
  // Import du script Spline
  import { onMount } from 'svelte';

  onMount(() => {
    // Charger le script Spline dynamiquement
    const script = document.createElement('script');
    script.type = 'module';
    script.src = 'https://unpkg.com/@splinetool/viewer@1.9.59/build/spline-viewer.js';
    document.head.appendChild(script);
  });
</script>

<svelte:head>
  <!-- Police Space Grotesk -->
  <link
    href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400&display=swap"
    rel="stylesheet" />
</svelte:head>

<div class="min-h-screen overflow-hidden bg-black">
  <!-- Section principale avec Spline et texte -->
  <div class="relative h-screen">
    <!-- Élément Spline -->
    <spline-viewer
      url="https://prod.spline.design/BknCtcxqfZULt3ch/scene.splinecode"
      loading="lazy"
      width="100%"
      height="100vh"
      background="transparent"
      auto-rotate="false"
      auto-play="true"
      style="width: 100%; height: 100%; position: absolute; top: 0; left: 0;">
    </spline-viewer>

    <!-- Texte centré par-dessus Spline -->
    <div class="absolute inset-0 flex flex-col items-center justify-center text-center">
      <h1
        class="-translate-x-3 translate-y-3 transform select-none text-[60px] font-light tracking-[3px] text-white drop-shadow-[0_0_20px_rgba(139,92,246,0.3)]"
        style="font-family: -apple-system, BlinkMacSystemFont, 'SF Pro Display', 'Segoe UI', system-ui, sans-serif;">
        CLONES
      </h1>
      <p
        class="mt-2 -translate-x-3 select-none text-center text-sm font-medium tracking-wide text-gray-400"
        style="font-family: -apple-system, BlinkMacSystemFont, 'SF Pro Display', 'Segoe UI', system-ui, sans-serif;">
        Soon...
      </p>
    </div>
  </div>
</div>
