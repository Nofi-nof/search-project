<script>
	import Pokemon from '../components/Pokemon.svelte';
	import Input from '../components/Input.svelte';

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
		},
		{
			name: 'フワリ',
			type: 'くさ',
			hp: 44,
			atk: 48,
			def: 65,
			sAtk: 50,
			sDef: 64,
			spd: 43
		},
		{
			name: 'ヒノアラシ',
			type: 'ほのお',
			hp: 44,
			atk: 48,
			def: 65,
			sAtk: 50,
			sDef: 64,
			spd: 43
		},
		{
			name: 'シズクガメ',
			type: 'みず',
			hp: 44,
			atk: 48,
			def: 65,
			sAtk: 50,
			sDef: 64,
			spd: 43
		}
	];

	$: includesPokemons = () => pokemons.filter((pokemon) => pokemon.name.includes(searchWord));
</script>

<div class="header">
	<img src="/src/images/logo.png" class="h-10 px-2" alt="pokemon-logo" />
	<Input bind:searchWord />
</div>

<main>
	{#each includesPokemons() as p}
		<Pokemon pokemon={p} />
	{/each}
</main>

<style>
	.header {
		align-items: center;
		display: flex;
		padding: 10px 10px 10px 10px;
	}
</style>
