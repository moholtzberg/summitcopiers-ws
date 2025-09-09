<script>
  import Modal from '$lib/components/Modal.svelte';

  let navOpen = $state(false);

  const toggleNav = () => {
    navOpen = !navOpen;
  };

  // Swap these with real assets when ready
  const models = $state([
    {
      name: "Kyocera TASKalfa 3554ci",
      blurb: "Color A3 MFP • 35 ppm • Robust finishing • App-enabled.",
      price: "$139/mo",
      cta: "Get This Deal",
      image: "/models/ta-3554ci.png"
    },
    {
      name: "Kyocera ECOSYS M3655idn",
      blurb: "B/W A4 • 57 ppm • Low TCO • Perfect for distributed teams.",
      price: "$79/mo",
      cta: "Get This Deal",
      image: "/models/mz-3200i.png"
    },
    {
      name: "Kyocera TASKalfa 5054ci",
      blurb: "Color A3 MFP • 50 ppm • Production-grade reliability.",
      price: "$189/mo",
      cta: "Get This Deal",
      image: "/models/ta-5054ci.png"
    }
  ]);

  const serviceAreas = [
    "Moffat County", "Routt County", "Grand County", "Garfield County",
    "Lake County", "Park County", "Chaffee County"
  ];

  function scrollToId(id) {
    const el = document.getElementById(id);
    if (el) el.scrollIntoView({ behavior: "smooth", block: "start" });
  }
</script>

<svelte:head>
  <title>Summit Copiers | Best Deals on Kyocera Copiers in the Colorado Rockies</title>
  <meta name="description" content="Summit Copiers delivers Kyocera copiers, printers, and managed print to the Colorado Rockies—fast installs, local service, and unbeatable lease pricing." />
  <meta name="viewport" content="width=device-width, initial-scale=1" />

  <!-- Open Graph -->
  <meta property="og:title" content="Summit Copiers | Kyocera in the Colorado Rockies" />
  <meta property="og:description" content="Unbeatable Kyocera copier leases & service across Summit & Eagle counties. Local. Reliable. Mountain-ready." />
  <meta property="og:type" content="website" />
  <meta property="og:url" content="https://www.summitcopiers.com" />
  <meta property="og:image" content="https://www.summitcopiers.com/og-image.jpg" />

  <!-- Brand colors (Navy / Slate / Pine) -->
  <meta name="theme-color" content="#0D2B45" />

  <!-- JSON-LD -->
  <script type="application/ld+json">
    {
      "@context":"https://schema.org",
      "@type":"LocalBusiness",
      "name":"Summit Copiers",
      "url":"https://www.summitcopiers.com",
      "logo":"https://www.summitcopiers.com/logo.svg",
      "image":"https://www.summitcopiers.com/og-image.jpg",
      "telephone":"+1-000-000-0000",
      "areaServed":[
        "Vail","Avon","Eagle","Edwards","Breckenridge","Frisco","Silverthorne",
        "Dillon","Aspen","Snowmass","Steamboat Springs","Glenwood Springs","Summit County","Eagle County"
      ],
      "makesOffer":[{"@type":"Offer","itemOffered":{"@type":"Product","name":"Kyocera TASKalfa & ECOSYS series"}}],
      "sameAs":[]
    }
  </script>
</svelte:head>

<!-- Page wrapper -->
<div class="min-h-screen bg-slate-400 text-slate-900 selection:bg-emerald-200/60">


  <!-- Hero -->
  <section class="relative overflow-hidden">
    <!-- Abstract mountain background -->
    <!-- <svg class="absolute text-black inset-0 -z-10 h-full w-full" viewBox="0 0 1440 560" preserveAspectRatio="none" aria-hidden="true">
      <defs>
        <linearGradient id="g1" x1="0" x2="1" y1="0" y2="1">
          <stop offset="0%" stop-color="#0D2B45"/>
          <stop offset="100%" stop-color="#274C5E"/>
        </linearGradient>
      </defs>
      <rect width="1440" height="560" fill="url(#g1)"></rect>
      <path d="M0,520 L240,360 L420,460 L600,300 L780,440 L960,320 L1200,420 L1440,300 L1440,560 L0,560 Z" fill="#123248" fill-opacity="0.5"></path>
      <path d="M0,540 L260,380 L420,460 L640,320 L860,460 L1100,360 L1300,430 L1440,360 L1440,560 L0,560 Z" fill="#155B4A" fill-opacity="0.25"></path>
    </svg> -->

    <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8 py-20 md:py-28 text-white bg-slate-500">
      <div class="max-w-2xl">
        <h1 class="text-4xl md:text-6xl font-extrabold leading-tight">
          Best Deals on <span class="text-emerald-300">Kyocera</span> Copiers in the Colorado Rockies
        </h1>
        <p class="mt-5 text-lg md:text-xl text-slate-200">
          Local delivery & installs across Summit and Eagle counties. Rugged reliability, low cost-per-page, and mountain-ready service—backed by Kyocera’s legendary durability.
        </p>
        <div class="mt-8 flex flex-col sm:flex-row gap-4">
          <a href="#contact" class="rounded-xl bg-emerald-500 px-6 py-3 font-semibold text-slate-900 hover:bg-emerald-400">
            Get My Quote
          </a>
          <a href="#models" class="rounded-xl border border-white/80 px-6 py-3 font-semibold hover:bg-white/60">
            See Current Deals
          </a>
        </div>
        <p class="mt-6 text-sm opacity-80">Fast installs • Lease or buy • Managed print • Local technicians</p>
      </div>
    </div>

    <img src="/summit-county.jpg" alt="" class="absolute bottom-0 left-1/2 -translate-x-1/2 w-full max-w-7xl opacity-20 bg-white/30 pointer-events-none select-none rounded-xl" />
  </section>

  <!-- Kyocera Deals -->
  <section id="models" class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8 py-16">
    <div class="flex items-end justify-between gap-6">
      <h2 class="text-2xl md:text-3xl font-bold text-slate-900">Featured Kyocera Deals</h2>
      <a href="#contact" class="hidden md:inline-block text-emerald-700 font-semibold hover:underline">Need a different model?</a>
    </div>

    <div class="mt-8 grid grid-cols-1 md:grid-cols-3 gap-6">
      {#each models as m}
        <article class="group rounded-2xl border border-slate-200 bg-white shadow-sm hover:shadow-md transition">
          <div class="aspect-[4/3] w-full overflow-hidden rounded-t-2xl bg-slate-100">
            <img src={m.image} alt={m.name} class="h-full w-auto mx-auto object-cover p-6" loading="lazy" />
          </div>
          <div class="p-6">
            <h3 class="font-semibold text-lg">{m.name}</h3>
            <p class="mt-2 text-slate-600">{m.blurb}</p>
            <div class="mt-4 flex items-center justify-between">
              <span class="text-xl font-bold text-slate-900">{m.price}</span>
              <a href="#contact" class="rounded-lg bg-slate-900 px-4 py-2 text-white font-medium group-hover:bg-[#0D2B45]">
                {m.cta}
              </a>
            </div>
          </div>
        </article>
      {/each}
    </div>

    <div class="mt-6 text-center md:hidden">
      <a href="#contact" class="text-emerald-700 font-semibold hover:underline">Need a different model?</a>
    </div>
  </section>

  <!-- Why Us -->
  <section id="why" class="bg-white">
    <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8 py-16">
      <h2 class="text-2xl md:text-3xl font-bold text-slate-900">Why Summit Copiers</h2>
      <div class="mt-8 grid grid-cols-1 md:grid-cols-3 gap-6">
        <div class="rounded-2xl border border-slate-200 p-6">
          <h3 class="font-semibold text-lg">Mountain-Local, Fast Response</h3>
          <p class="mt-2 text-slate-600">Technicians based in Summit & Eagle counties. We know the terrain, weather, and what “urgent” means during season.</p>
        </div>
        <div class="rounded-2xl border border-slate-200 p-6">
          <h3 class="font-semibold text-lg">Unbeatable Kyocera Pricing</h3>
          <p class="mt-2 text-slate-600">Flexible leases and transparent CPC. We’ll beat any comparable Kyocera quote in the Rockies.</p>
        </div>
        <div class="rounded-2xl border border-slate-200 p-6">
          <h3 class="font-semibold text-lg">Managed Print That Just Works</h3>
          <p class="mt-2 text-slate-600">Automated supplies, remote monitoring, workflow apps, and set-and-forget reliability.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Service Areas -->
  <section id="areas" class="bg-slate-900 text-white">
    <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8 py-16">
      <div class="flex items-end justify-between gap-6">
        <h2 class="text-2xl md:text-3xl font-bold">Serving All Mountain Towns</h2>
        <span class="hidden md:inline-block text-emerald-300">Same-week installs available</span>
      </div>
      <p class="mt-4 text-lg text-slate-300">We serve all mountain towns and the following counties:</p>
      <ul class="mt-6 grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-3">
        {#each serviceAreas as county}
          <li class="rounded-xl border border-white/10 bg-white/5 px-4 py-3">{county}</li>
        {/each}
      </ul>
    </div>
  </section>

  <!-- Contact / Quote -->
  <section id="contact" class="bg-gradient-to-b from-slate-50 to-white">
    <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8 py-16">
      <div class="grid grid-cols-1 md:grid-cols-2 gap-10 items-start">
        <div>
          <h2 class="text-2xl md:text-3xl font-bold text-slate-900">Get a Fast Quote</h2>
          <p class="mt-3 text-slate-600">Tell us a bit about your team and print volume—we’ll recommend the right Kyocera and deliver/install on your schedule.</p>
          <div class="mt-6 space-y-3 text-slate-700">
            <div class="flex items-center gap-3">
              <span class="inline-flex h-8 w-8 items-center justify-center rounded-full bg-emerald-100 text-emerald-700">1</span>
              <p>Share basic info (team size, monthly pages, color vs B/W)</p>
            </div>
            <div class="flex items-center gap-3">
              <span class="inline-flex h-8 w-8 items-center justify-center rounded-full bg-emerald-100 text-emerald-700">2</span>
              <p>Pick your lease or purchase option (we’ll show total cost)</p>
            </div>
            <div class="flex items-center gap-3">
              <span class="inline-flex h-8 w-8 items-center justify-center rounded-full bg-emerald-100 text-emerald-700">3</span>
              <p>Schedule delivery & install—often same week</p>
            </div>
          </div>
        </div>

        <!-- Simple no-backend form (wire to your endpoint later) -->
        <form class="rounded-2xl border border-slate-200 bg-white p-6 shadow-sm">
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
            <div>
              <label class="block text-sm font-medium text-slate-700">Name</label>
              <input required class="mt-1 w-full rounded-lg border-slate-300 focus:border-emerald-500 focus:ring-emerald-500" placeholder="Jane Doe" />
            </div>
            <div>
              <label class="block text-sm font-medium text-slate-700">Company</label>
              <input class="mt-1 w-full rounded-lg border-slate-300 focus:border-emerald-500 focus:ring-emerald-500" placeholder="Acme Resorts" />
            </div>
            <div>
              <label class="block text-sm font-medium text-slate-700">Email</label>
              <input type="email" required class="mt-1 w-full rounded-lg border-slate-300 focus:border-emerald-500 focus:ring-emerald-500" placeholder="you@company.com" />
            </div>
            <div>
              <label class="block text-sm font-medium text-slate-700">Phone</label>
              <input class="mt-1 w-full rounded-lg border-slate-300 focus:border-emerald-500 focus:ring-emerald-500" placeholder="(555) 555-5555" />
            </div>
            <div class="sm:col-span-2">
              <label class="block text-sm font-medium text-slate-700">Where are you located?</label>
              <input class="mt-1 w-full rounded-lg border-slate-300 focus:border-emerald-500 focus:ring-emerald-500" placeholder="e.g., Breckenridge, CO" />
            </div>
            <div class="sm:col-span-2">
              <label class="block text-sm font-medium text-slate-700">Notes</label>
              <textarea rows="4" class="mt-1 w-full rounded-lg border-slate-300 focus:border-emerald-500 focus:ring-emerald-500" placeholder="Monthly pages, color vs B/W, finishing needs..." />
            </div>
          </div>
          <button type="submit" class="mt-5 w-full rounded-xl bg-emerald-600 px-6 py-3 font-semibold text-white hover:bg-emerald-700">
            Request My Quote
          </button>
          <p class="mt-3 text-center text-xs text-slate-500">By submitting, you agree to be contacted about your quote.</p>
        </form>
      </div>
    </div>
  </section>

</div>
