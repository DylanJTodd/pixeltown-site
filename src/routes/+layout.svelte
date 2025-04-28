<script>
	import Header from '$lib/header/Header.svelte';
	import { webVitals } from '$lib/vitals';
	import { browser } from '$app/env';
	import { page } from '$app/stores';
	import '../app.css';

  let analyticsId = import.meta.env.VERCEL_ANALYTICS_ID;

  $: if (browser && analyticsId) {
    webVitals({
      path: $page.url.pathname,
      params: $page.params,
      analyticsId
    })
  }
</script>

<Header />

<main>
	<slot />
</main>

<footer style="display: grid; grid-template-columns: 1fr 1fr; align-items: start; gap: 1rem; margin-right: 1rem; margin-bottom: 5px; padding-top: 5px;">
  <div>
      <p><b style="font-size: 120%;">Copyright PixelTown 2025. All Rights Reserved</b></p><br>
      <p>PixelTown is in no way affiliated with Mojang, AB.</p>
      <p>Nor should it be considered a company endorsed or affiliated by Mojang, AB.</p>
      <p>Any purchase made on this store goes to PixelTown</p>
  </div>

  <div style="display: flex; flex-direction: column; gap: 0.5rem; font-size: 80%; align-items: flex-end; padding-top: 5px; font-weight: 600;">
      <a href="/" target="_blank" style="text-decoration: underline; color: #333;">Terms and Conditions</a>
      <a href="/" target="_blank" style="text-decoration: underline; color: #333;">Privacy Policy</a>
      <a href="/" target="_blank" style="text-decoration: underline; color: #333;">Refund Policy</a>
      <a href="/" target="_blank" style="text-decoration: underline; color: #333;">Contact</a>
      <a href="mailto:pixeltownbusiness@gmail.com" style="margin-top: 2rem; font-size: 80%; text-decoration: none; color: #333;">For business inquiries, contact <span>pixeltownbusiness@gmail.com</span></a>
  </div>
</footer>

<style>
</style>
