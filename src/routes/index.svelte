<script context="module">
	export async function load({ fetch }) {
		const url = `https://pokeapi.co/api/v2/pokemon?limit=150`;
		const res = await fetch(url);
		const data = await res.json();

		const loadedPokemon = data.results.map((pmon, index) => {
			return {
				name: pmon.name,
				id: index + 1,
				image: `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/${
					index + 1
				}.png`
			};
		});

		return { props: { pokemon: loadedPokemon } };
	}
</script>

<script>
	import PokeCard from '../components/pokeCard.svelte';
	export let pokemon;
	let searchTerm = '';
	let filteredPokemon = [];

	$: {
		if (searchTerm) {
			filteredPokemon = pokemon.filter((poke) =>
				poke.name.toLowerCase().includes(searchTerm.toLowerCase())
			);
		} else {
			filteredPokemon = [...pokemon];
		}
	}
</script>

<svelte:head>
	<title>Svelte Kit Pokedex</title>
</svelte:head>
<h1 class="text-center font-extrabold text-3xl">Pokedex</h1>
<div class="max-w-3xl mx-auto flex items-center my-2 shadow shadow-green-700">
	<input
		bind:value={searchTerm}
		type="text"
		class="border rounded p-3 w-full border-green-500 border-opacity-30"
		placeholder="Search for a pokemon"
	/>
</div>
<div class="grid grid-cols-3 md:grid-cols-4 lg:grid-cols-6 gap-3 w-full">
	{#each filteredPokemon as poke}
		<PokeCard {poke} />
	{/each}
</div>
