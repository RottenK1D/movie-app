<script context="module">
	export async function load({ fetch, params }) {
		const respond = await fetch(
			`https://api.themoviedb.org/3/movie/${params.id}?api_key=bf923b2b075b406689035c073e24cfe4&language=en-US`
		);
		const movieDescription = await respond.json();
		return { props: { movieDescription } };
	}
</script>

<script>
	import MoviesDescription from '../../lib/Movies_Description.svelte';
	export let movieDescription;
</script>

<MoviesDescription {movieDescription}/>