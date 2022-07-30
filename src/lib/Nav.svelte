<script>
	import Search from '../lib/Search.svelte';
	let menu = false;
	function showMenu() {
		menu = menu === false ? true : false;
	}
</script>

<div class="navbar mb-2 shadow-lg bg-neutral text-neutral-content font-mono">
	<div class="flex-none px-2 mx-2">
		<button on:click={showMenu}><span class="text-2xl font-bold">Movies</span></button>
	</div>
	<div class="flex-1 px-2 mx-2">
		<div class="items-stretch">
			{#if menu}
				<a href="/" class="btn btn-ghost btn-sm rounded-btn">popular</a>
			{/if}
		</div>
	</div>

	<Search />
</div>
