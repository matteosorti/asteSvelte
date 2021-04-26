<script>
    import {link} from 'svelte-spa-router'
    export let titolo, descrizione, idopera, idartista, foto, creazione, scaduto, scadenza;
    let valore="";

    
    async function offerta(){
      const {idutente}=JSON.parse(sessionStorage.getItem("utente"));
      const result2=await axios.post("http://localhost:8090/projectwork/rest/utenteHasOpera/update", {
        valore, idutente
      })
    }
</script>

<section class="text-gray-600 body-font overflow-hidden">
    <div class="container px-5 py-24 mx-auto">
      <div class="lg:w-4/5 mx-auto flex flex-wrap">
        <div class="lg:w-1/2 w-full lg:pr-10 lg:py-6 mb-6 lg:mb-0">
          <h3 class="text-sm title-font text-gray-500 tracking-widest">ASTALAVISTA</h3>
          <h1 class="text-gray-900 text-3xl title-font font-medium mb-4">{titolo}</h1>
          <h2 class="text-sm title-font text-gray-500 tracking-widest">{idartista}</h2>
          <div class="flex mb-4">
            <span class="flex-grow text-yellow-500 border-b-2 border-yellow-500 py-2 text-lg px-1">Description</span>
          </div>
          <p class="leading-relaxed mb-4">{descrizione}</p>
          
          <div class="flex">
            {#if scaduto==0}
            <input bind:value={valore} type="text" id="valore" name="valore" class="w-full bg-white rounded border border-gray-300 focus:border-yellow-500 focus:ring-2 focus:ring-yellow-200 text-base outline-none text-gray-700 py-1 px-3 leading-8 transition-colors duration-200 ease-in-out">
            <button on:click={offerta} class="flex ml-auto text-white bg-yellow-500 border-0 py-2 px-6 focus:outline-none hover:bg-yellow-600 rounded">Offerta</button>
            {/if}
            {#if scaduto==1}
            
            <input disabled=true bind:value={valore} type="text" id="valore" name="valore" class="w-full bg-white rounded border border-gray-300 focus:border-yellow-500 focus:ring-2 focus:ring-yellow-200 text-base outline-none text-gray-700 py-1 px-3 leading-8 transition-colors duration-200 ease-in-out" placeholder="asta scaduta">
            <button disabled=true on:click={offerta} class="flex ml-auto text-white bg-yellow-500 border-0 py-2 px-6 focus:outline-none hover:bg-yellow-600 rounded">Offerta</button>
            {/if}
          </div>
        </div>
        <img alt="ecommerce" class="lg:w-1/2 w-full lg:h-auto h-64 object-cover object-center rounded" src="{foto}">
      </div>
    </div>
  </section>