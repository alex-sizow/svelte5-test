<script>
	class Temperature {
		#c = $state(0);
		#f = $state(0);

		get c() {
			return this.#c;
		}

		set c(c) {
			this.#c = c;
			this.#f = c * (9 / 5) + 32;
		}

		get f() {
			return this.#f;
		}

		set f(f) {
			this.#f = f;
			this.#c = (f - 32) * (5 / 9);
		}
	}

	const temperature = new Temperature();
</script>

<h1>Temperature converter</h1>
<section>
	<input type="number" bind:value={temperature.c} /> Celsius <span>=</span>
	<input type="number" bind:value={temperature.f} />Fahrenheit
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
