<script>
	import Pokemon from '../components/Pokemon.svelte';

	//let json = [];

	//const fetchPokemons = async () => {
	//const res = await fetch('https://zukan.pokemon.co.jp/zukan-api/api/search/?limit=64&page=1');
	//json = await res.json().results;
	//};

	//fetchPokemons();

	const url = 'https://zukan.pokemon.co.jp/zukan-api/api/search/?limit=64&page=1';
	fetch(url)
		.then(function (response) {
			return response.text();
		})
		.then(function (text) {
			console.log(text);
		});

	let script = document.createElement('script');

	script.src = 'https://zukan.pokemon.co.jp/zukan-api/api/search/?limit=64&page=1';
	document.body.appendChild(script);
	document.body.removeChild(script);

	function jsonData(data) {
		let result = data.results[0];
		let name = document.getElementById('name');

		name.textContent = result.name;
	}
</script>

<main>
	<p id="name" />
	<!--	{#each json as j}
		<Pokemon pokemon={j} />
	{/each}-->
</main>
