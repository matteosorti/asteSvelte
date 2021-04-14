<script>
    import {link} from 'svelte-spa-router'
    import { onMount } from 'svelte';
    import axios from 'axios';
    import Home from './Home.svelte'
    import DettaglioOpera from './DettaglioOpera.svelte'
    import Opera from './Opera.svelte';


    let opera = {}
    export let params = {}
    console.log(params.id);
     onMount(async()=>{
       console.log("montato")
       const result=await axios.post("http://localhost:8090/projectwork/rest/opera/findAllById/"+params.id)
       console.log(result);
       opera=result.data.result;
     })
</script>

<DettaglioOpera titolo={opera.titolo} descrizione={opera.descrizione} idopera={opera.idopera} idartista={opera.idartista}/>