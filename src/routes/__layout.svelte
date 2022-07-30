<script>
	import 'virtual:windi.css';
	import '../app.css';
	import Nav from '../lib/Nav.svelte';
</script>

<svelte:head>
	<title>Movie DB</title>
</svelte:head>

<Nav />
<slot />
