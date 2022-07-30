<script context="module">
	export async function load({ fetch, params }) {
		const respond = await fetch(
			`https://api.themoviedb.org/3/search/movie?api_key=bf923b2b075b406689035c073e24cfe4&language=en-US&query=${params.id}&page=1&include_adult=false`
		);
		const data = await respond.json();
		return { props: { searchMovies: data.results } };
	}
</script>

<script>
	import PopularMovies from "../../lib/PopularMovies.svelte";
	export let searchMovies;
</script>

<div class="grid justify-items-center place-content-center gap-y-26 gap-x-2 m-8">
	{#each searchMovies as movie}
		<PopularMovies {movie} />
	{/each}
</div>

<style>
	.grid {
		grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
	}
</style>

