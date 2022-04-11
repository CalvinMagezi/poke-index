<script>
	import { fade } from 'svelte/transition';
	export let poke;
</script>

<a href={`/pokemon/${poke.id}`}>
	<div
		class="bg-gray-500 bg-opacity-30 flex cursor-pointer transition duration-200 hover:scale-105 ease-in-out flex-col items-center justify-center space-y-1 border border-black border-opacity-30 rounded-lg shadow-lg my-1"
		transition:fade
	>
		<img src={poke.image} alt={poke.name} />
		<p>{poke.id}. {poke.name}</p>
	</div>
</a>
