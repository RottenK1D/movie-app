<script>
	export let movieDescription;
</script>

<div class="sm:mx-[20%] sm:my-4 <sm:m-4 font-mono">
	<div class="w-full">
		<img
			src={'https://image.tmdb.org/t/p/original' + movieDescription.backdrop_path}
			alt={movieDescription.title}
			class="w-full rounded-lg"
		/>
	</div>

	<div class="py-2 ">
		<h1 class="text-xl font-semibold">{movieDescription.title}</h1>
		<div class="pb-2 text-base border-b-2">{movieDescription.overview}</div>
		<div class="text-sm italic pt-2">
			<div class="">Date: {movieDescription.release_date}</div>
			<div class="">Budget: ${movieDescription.budget}</div>
			<div class="">Rating: {movieDescription.vote_average}</div>
			<div class="">Runtime: {movieDescription.runtime} mins</div>
		</div>
	</div>
</div>
