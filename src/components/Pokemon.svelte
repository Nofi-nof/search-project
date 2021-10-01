<script>
	import Bar from '../components/Bar.svelte';

	export let pokemon;

	const typeToClass = {
		type_1: 'glass',
		type_2: 'fire'
	};

	let open = false;
	const toggle = () => (open = !open);
</script>

<div class="pokemon {typeToClass[pokemon.type]}" on:click={toggle}>
	<h2>{pokemon.name}</h2>
	{#if open}
		<div class="status">
			<h3>ステータス</h3>
			<Bar label="重さ" value={pokemon.omosa} />
			<Bar label="高さ" value={pokemon.takasa} />
			<Bar label="タイプ１" value={pokemon.type_1} />
			<Bar label="タイプ２" value={pokemon.type_2} />
		</div>
	{:else}
		<div>クリックで詳細を見る</div>
	{/if}
</div>

<style>
	h2,
	h3 {
		font-weight: normal;
	}

	.pokemon {
		color: white;
		padding: 1em;
		cursor: pointer;
	}

	.glass {
		background-color: rgb(96, 184, 69);
	}

	.fire {
		background-color: rgb(226, 82, 82);
	}
</style>
