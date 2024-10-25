<script>
	let c = $state(0);
	let f = $state(0);
</script>

<h1>Temperature converter</h1>
<section>
	<input type="number" bind:value={c} /> Celsius =
	<input type="number" bind:value={f} /> Fahrenheit
</section>

<style scoped>
	h1 {
		display: flex;
		justify-content: center;
		font-size: 34px;
		color: white;
		margin-top: 100px;
		margin-bottom: 20px;
	}
	section {
		display: flex;
		justify-content: center;
		gap: 20px;
		font-size: 34px;
		color: white;
		> input[type='number'] {
			color: black;
			max-width: 100px;
			background-color: bisque;
			border-radius: 10px;
			padding: 5px;
			font-size: 24px;
		}
	}
</style>
