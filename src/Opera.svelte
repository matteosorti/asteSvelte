<script>
    import {link} from 'svelte-spa-router'
    export let titolo,descrizione, idopera, foto, creazione, scadenza, scaduto;
</script>

<section class="text-gray-600 body-font">
    <div class="container px-5 py-24 mx-auto">
      <div class="flex flex-wrap sm:-m-4 -mx-4 -mb-10 -mt-4">
        <div class="p-4 md:w-1/3 sm:mb-0 mb-6">
          <div class="rounded-lg h-64 overflow-hidden">
            <img alt="content" class="object-cover object-center h-full w-full" src="{foto}">
          </div>
          <h2 class="text-xl font-medium title-font text-gray-900 mt-5">{titolo}</h2>
          <h2 class="text-xl font-medium title-font text-gray-900 mt-5">Scadenza: {scadenza}</h2>
          <p class="text-base leading-relaxed mt-2">{descrizione}</p>
          <a href="/dettaglio/{idopera}" use:link class="text-yellow-500 inline-flex items-center mt-3">Fai la tua offerta
            <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" class="w-4 h-4 ml-2" viewBox="0 0 24 24">
              <path d="M5 12h14M12 5l7 7-7 7"></path>
            </svg>
          </a>
        </div>
      </div>
    </div>
  </section>