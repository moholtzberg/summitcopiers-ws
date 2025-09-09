<script>
	import '../app.css';
	let { children } = $props();
  import Navigation from '$lib/components/Navigation.svelte';

  let navOpen = $state(false);

  const toggleNav = () => {
    navOpen = !navOpen;
  };

  const scrollToId = (id) => {
    const el = document.getElementById(id);
    if (el) el.scrollIntoView({ behavior: "smooth", block: "start" });
  }
</script>

<!-- <Navigation /> -->


<div class="min-h-screen flex flex-col bg-slate-50">

    <header class="sticky top-0 z-30 backdrop-blur bg-white/70 border-b border-slate-200">
      <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8 h-16 flex items-center justify-between">
        <a href="/" class="flex items-center gap-3">
          <!-- Inline logo mark (abstract mountain) -->
          <svg class="h-8 w-8 text-[#0D2B45]" viewBox="0 0 24 24" fill="none" aria-hidden="true">
            <path d="M3 18l6-9 3 4 3-4 6 9H3z" stroke="currentColor" stroke-width="2" fill="none" />
          </svg>
          <span class="font-bold tracking-tight text-lg md:text-xl">Summit Copiers</span>
        </a>

        <nav class="hidden md:flex items-center gap-8 text-sm">
          <button class="hover:text-slate-700" onclick={() => scrollToId('models')}>Kyocera Deals</button>
          <button class="hover:text-slate-700" onclick={() => scrollToId('why')}>Why Us</button>
          <button class="hover:text-slate-700" onclick={() => scrollToId('areas')}>Service Areas</button>
          <button class="hover:text-slate-700" onclick={() => scrollToId('contact')}>Contact</button>
          <a href="#contact" class="rounded-xl bg-emerald-600 px-4 py-2 font-semibold text-white hover:bg-emerald-700">Get a Quote</a>
        </nav>

        <button class="md:hidden p-2" aria-label="Toggle menu" onclick={() => toggleNav()}>
          <svg class="h-6 w-6" viewBox="0 0 24 24" fill="none">
            <path d="M3 7h18M3 12h18M3 17h18" stroke="currentColor" stroke-width="2" />
          </svg>
        </button>
      </div>
      {#if navOpen}
        <div class="md:hidden border-t border-slate-200 bg-white">
          <div class="px-4 py-3 flex flex-col gap-2">
            <a href="#models" class="py-2" onclick={() => (navOpen = false)}>Kyocera Deals</a>
            <a href="#why" class="py-2" onclick={() => (navOpen = false)}>Why Us</a>
            <a href="#areas" class="py-2" onclick={() => (navOpen = false)}>Service Areas</a>
            <a href="#contact" class="py-2" onclick={() => (navOpen = false)}>Contact</a>
            <a href="#contact" class="mt-2 rounded-xl bg-emerald-600 px-4 py-2 font-semibold text-white text-center">Get a Quote</a>
          </div>
        </div>
      {/if}
    </header>

    {@render children()}

    <footer class="border-t border-slate-200 bg-white">
      <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8 py-10 text-sm text-slate-600">
        <div class="flex flex-col md:flex-row justify-between gap-6">
          <div class="max-w-md">
            <div class="flex items-center gap-3">
              <svg class="h-6 w-6 text-[#0D2B45]" viewBox="0 0 24 24" fill="none" aria-hidden="true">
                <path d="M3 18l6-9 3 4 3-4 6 9H3z" stroke="currentColor" stroke-width="2" fill="none" />
              </svg>
              <span class="font-semibold text-slate-900">Summit Copiers</span>
            </div>
            <p class="mt-3">Kyocera copiers & managed print for the Colorado Rockies. Local delivery, pro installs, and responsive service.</p>
          </div>
          <div class="grid grid-cols-2 gap-8">
            <div>
              <div class="font-semibold text-slate-900">Explore</div>
              <ul class="mt-3 space-y-2">
                <li><a href="#models" class="hover:underline">Deals</a></li>
                <li><a href="#why" class="hover:underline">Why Us</a></li>
                <li><a href="#areas" class="hover:underline">Service Areas</a></li>
                <li><a href="#contact" class="hover:underline">Contact</a></li>
              </ul>
            </div>
            <div>
              <div class="font-semibold text-slate-900">Contact</div>
              <ul class="mt-3 space-y-2">
                <li>Summit County, CO</li>
                <li><a class="hover:underline" href="tel:+19704180055">(970) 418-0055</a></li>
                <li><a class="hover:underline" href="mailto:hello@summitcopiers.com">hello@summitcopiers.com</a></li>
              </ul>
            </div>
          </div>
        </div>
        <p class="mt-8 text-xs text-slate-400">© {new Date().getFullYear()} Summit Copiers. Kyocera® trademarks are property of their respective owners.</p>
      </div>
    </footer>

</div>
