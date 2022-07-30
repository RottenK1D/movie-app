<script>
	import PopularMovies from './PopularMovies.svelte';
	export let movies;
</script>

<main class="font-mono">
	<div class="grid justify-items-center place-content-center gap-y-26 gap-x-2 m-8">
		{#each movies as movie}
			<PopularMovies {movie} />
		{/each}
	</div>
</main>

<style>
	.grid {
		grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
	}
</style>
