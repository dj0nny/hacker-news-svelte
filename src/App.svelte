<script>
import { Route, Router } from 'svero';
import Header from './components/Header.svelte';
import News from './pages/News.svelte';
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
}

</style>

<div id="app-container">
	<Header />
	<Router>
		<Route path="*" component={News} ></Route>
		<Route path="/newest" component={Newest} ></Route>
	</Router>
</div>

