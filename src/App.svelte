<script lang="ts">
	import Router from "svelte-spa-router";
	import { wrap } from "svelte-spa-router/wrap";
	import Index from "./Index.svelte";
	import NotFound from "./NotFound.svelte";

	const routes = {
		"/": Index,
		"/login": wrap({
			asyncComponent: () => import("./Login.svelte"),
		}),
		"*": NotFound,
	};
</script>

<Router {routes} />
