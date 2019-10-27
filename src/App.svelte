<script>
import { Route, Router } from 'svero';

import Header from './components/Header.svelte';
import Index from './pages/Index.svelte';
import Newest from './pages/Newest.svelte';
</script>

<style>
:global(body) {
	background: #fff;
	font-family: Verdana, Geneva, sans-serif;
}

#app-container {
	background: rgb(246, 246, 239);
	width: 80%;
	margin: auto;
	counter-reset: news;
}

</style>

<div id="app-container">
	<Header />
	<Router>
		<Route path="/news" component={Index} />
		<Route path="/newest" component={Newest} />
	</Router>
</div>

