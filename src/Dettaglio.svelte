<script>
    import {link} from 'svelte-spa-router'
    import { onMount } from 'svelte';
    import axios from 'axios';
    import DettaglioOpera from './DettaglioOpera.svelte'
    import Opera from './Opera.svelte';

    let opere = []
    onMount(async()=>{
      console.log("montato")
      const result=await axios.get("http://localhost:8090/projectwork/rest/opera/findAllById", {idopera})
      console.log(result);
      opere=result.data.result;
    })
</script>

{#each opere as opera}
 <DettaglioOpera titolo={opera.titolo} descrizione={opera.descrizione} idopera={opera.idopera} idartista={opera.idartista}/>
{/each}