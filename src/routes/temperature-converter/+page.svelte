<script>
	let c = $state(0);
	let f = $state(0);
</script>

<h1>Temperature converter</h1>
<section>
	<input type="number" bind:value={c} /> Celsius <span>=</span>
	<input type="number" bind:value={f} />Fahrenheit
</section>

<style scoped>
	h1 {
		display: flex;
		justify-content: center;
		font-size: 44px;
		font-weight: 700;
		color: white;
		margin-top: 100px;
		margin-bottom: 20px;
		font-family: Arial, sans-serif;
	}
	section {
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 20px;
		font-size: 34px;
		color: white;
		font-family: Arial, sans-serif;

		span {
			padding-top: 1px;
			font-size: 50px;
		}
		> input[type='number'] {
			color: black;
			font-size: 34px;
			max-width: 100px;
			background-color: bisque;
			border-radius: 10px;
			padding: 10px;
			font-size: 24px;
		}
	}
</style>
