<script>
	import Router, {location} from 'svelte-spa-router'
	import Home from "./Home.svelte"
	import Login from "./Login.svelte"
	import Signup from "./Signup.svelte"
	import Footer from "./Footer.svelte"
	let routes = {
		'/': Home,
		'/login': Login,
		'/signup': Signup,
	}
</script>

<Router {routes}/>


{#if ($location!=="/login")&&($location!=="/signup")}
<Footer />
{/if}