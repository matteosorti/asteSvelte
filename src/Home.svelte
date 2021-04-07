<script>
    import {link} from 'svelte-spa-router'
    import { onMount } from 'svelte';
    import axios from 'axios';
    import Opera from './Opera.svelte'

    let opere = []
    onMount(async()=>{
      console.log("montato")
      const result=await axios.get("http://localhost:8090/projectwork/rest/opera/findAll")
      console.log(result);
      opere=result.data.result;
    })
</script>

<a href="/login" use:link>logout</a>
{#each opere as opera}
 <Opera titolo={opera.titolo} descrizione={opera.descrizione}/>
{/each}
