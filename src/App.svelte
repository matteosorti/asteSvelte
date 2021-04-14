<script>
	import Router, {location} from 'svelte-spa-router'
	import Home from "./Home.svelte"
	import Dettaglio from "./Dettaglio.svelte"
	import Login from "./Login.svelte"
	import Signup from "./Signup.svelte"
	import Footer from "./Footer.svelte"
	import Header from "./Header.svelte"
	let routes = {
		'/': Home,
		'/dettaglio/:id': Dettaglio,
		'/login': Login,
		'/signup': Signup,
	}
</script>

{#if ($location!=="/login")&&($location!=="/signup")}
<Header />
{/if}


<Router {routes}/>


{#if ($location!=="/login")&&($location!=="/signup")}
<Footer />
{/if}