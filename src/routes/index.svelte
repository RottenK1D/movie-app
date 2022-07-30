<script context="module">
	export async function load({ fetch }) {
		const respond = await fetch(
			`https://api.themoviedb.org/3/movie/popular?api_key=bf923b2b075b406689035c073e24cfe4&language=en-US`
		);
		const data = await respond.json();
		return { props: { movies: data.results } };
	}
</script>

<script>
	import Movies from '../lib/Movies.svelte';
	export let movies;
</script>

<Movies {movies} />
