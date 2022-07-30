<script>
	import { goto } from '$app/navigation';
	let inputValue = '';
	let search = false;
	let active = false;

	function submitSearch() {
		goto('/search/' + inputValue);
	}

	function showSearch() {
		search = search === false ? true : false;
	}

	function cancelInactive() {
		if (inputValue) {
			active = true;
		} else {
			active = false;
		}
	}
</script>

<form on:submit|preventDefault={submitSearch}>
	{#if !active}
		<label for="search_movie" />
	{/if}
	<div class="flex-1 lg:flex-none">
		<div class="form-control">
			{#if search}
				<input
					on:blur={cancelInactive}
					on:focus={() => (active = true)}
					bind:value={inputValue}
					name="search_movie"
					type="text"
					placeholder="search"
					class="input input-ghost "
				/>
			{/if}
		</div>
	</div>
	<div class="flex-none">
		<button on:click|once={showSearch} class="btn btn-square btn-ghost">
			<svg
				xmlns="http://www.w3.org/2000/svg"
				fill="none"
				viewBox="0 0 24 24"
				class="inline-block w-6 h-6 stroke-current"
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"
				/>
			</svg>
		</button>
	</div>
</form>
