<script>
	import Pokemon from './Pokemon.svelte';
	import Input from './Input.svelte';

	let searchWord = '';

	const pokemons = [
		{
			name: 'フシギダネ',
			type: 'くさ',
			hp: 45,
			atk: 49,
			def: 49,
			sAtk: 65,
			sDef: 65,
			spd: 45
		},
		{
			name: 'ヒトカゲ',
			type: 'ほのお',
			hp: 39,
			atk: 52,
			def: 43,
			sAtk: 60,
			sDef: 50,
			spd: 65
		},
		{
			name: 'ゼニガメ',
			type: 'みず',
			hp: 44,
			atk: 48,
			def: 65,
			sAtk: 50,
			sDef: 64,
			spd: 43
		}
	];

	$: filterPokemons = () => pokemons.filter((pokemon) => pokemon.name === searchWord);
</script>

<Input bind:searchWord />

<main>
	{#each filterPokemons() as p}
		<Pokemon pokemon={p} />
	{/each}
</main>
