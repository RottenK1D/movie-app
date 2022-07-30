<script>
	export let movie;
	console.log(movie);
</script>

<div class="flex flex-col justify-between p-4 ">
	<a href={'/movie/' + movie.id}
		><img
			src={'https://image.tmdb.org/t/p/original' + movie.poster_path}
			alt={movie.title}
			class="w-full h-[500px] object-cover rounded-lg"
		/></a
	>
	<div class="h-10">
		<div class="text-xl mt-6 font-medium">{movie.title}</div>
		<div class="text-base">{movie.release_date}</div>
	</div>
</div>
