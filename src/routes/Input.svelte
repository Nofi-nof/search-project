<script>
	export let searchWord;
</script>

<input bind:value={searchWord} class="poke-input" placeholder="ポケモン検索" />

<style>
	.poke-input {
		position: relative;
		border-radius: 5px;
		padding-left: 3px;
		border: thick double #000000;
	}
</style>
