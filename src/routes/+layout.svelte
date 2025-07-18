<script lang="ts">
  import '../app.css';
  import { page } from '$app/state';

  let { children } = $props();

  const title = $derived.by(() => {
    let pre = 'CLONES';
    const route = page.route.id?.split('/')[1];
    if (route) {
      pre += ' - ' + route[0].toUpperCase() + route.slice(1, route.length);
    }
    return pre;
  });
</script>

<svelte:head>
  <!-- HTML Meta Tags -->
  <title>{title}</title>
  <meta name="description" content="Train. Tokenize. Execute." />

  <!-- Facebook Meta Tags -->
  <meta property="og:url" content={page.url.toString()} />
  <meta property="og:type" content="website" />
  <meta property="og:title" content={title} />
  <meta property="og:description" content="Train. Tokenize. Execute." />
  <meta property="og:image" content="https://clones-ai.com/favicon.png" />

  <!-- Twitter Meta Tags -->
  <meta name="twitter:card" content="summary_large_image" />
  <meta property="twitter:domain" content="clones-ai.com" />
  <meta property="twitter:url" content={page.url.toString()} />
  <meta name="twitter:title" content={title} />
  <meta name="twitter:description" content="Train. Tokenize. Execute." />
  <meta name="twitter:image" content="https://clones-ai.com/favicon.png" />
</svelte:head>

<div class="min-h-screen bg-black">
  {@render children()}
  <!-- Google tag (gtag.js) -->
  <script async src="https://www.googletagmanager.com/gtag/js?id=G-TQ5Z1BBEGG"></script>
  <script>
    window.dataLayer = window.dataLayer || [];
    function gtag() {
      dataLayer.push(arguments);
    }
    gtag('js', new Date());

    gtag('config', 'G-TQ5Z1BBEGG');
  </script>
</div>
