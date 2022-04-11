<script context="module">
	export async function load({ fetch, params }) {
		const id = params.id;
		const url = `https://pokeapi.co/api/v2/pokemon/${id}`;
		const res = await fetch(url);
		const poke = await res.json();
		return { props: { poke } };
	}
</script>

<script>
	import { fade } from 'svelte/transition';
	export let poke;
	const type = poke.types[0].type.name;
	let pokecolor = 'shadow-green-500';

	$: {
		if (type) {
			switch (type) {
				case 'bug':
					pokecolor = 'shadow-green-700';
					break;
				case 'grass':
					pokecolor = 'shadow-green-500';
					break;
				case 'fire':
					pokecolor = 'shadow-red-500';
					break;
				case 'water':
					pokecolor = 'shadow-blue-500';
					break;
				case 'normal':
					pokecolor = 'shadow-gray-500';
					break;
				case 'poison':
					pokecolor = 'shadow-purple-500';
					break;
				case 'ground':
					pokecolor = 'shadow-orange-700';
					break;
				case 'rock':
					pokecolor = 'shadow-orange-800';
					break;
				case 'fighting':
					pokecolor = 'shadow-red-700';
					break;
				case 'electric':
					pokecolor = 'shadow-yellow-500';
					break;

				default:
					pokecolor = 'shadow-gray-300';
					break;
			}
		} else {
			pokecolor = 'shadow-green-500';
		}
	}
</script>

<div class="border border-black rounded-full p-3">
	<div
		class="flex flex-col items-center justify-center space-y-2 border border-black rounded-full p-3 shadow-lg {pokecolor} "
		transition:fade
	>
		<img src={poke.sprites['front_default']} class="h-64" alt="" />
		<h1 class="text-4xl font-extrabold text-center uppercase">{poke.name}</h1>
		<p>
			Type: <strong class="uppercase">{type}</strong> | Height:
			<strong>{poke.height}</strong> | Weight: <strong>{poke.weight}</strong>
		</p>
	</div>
</div>
