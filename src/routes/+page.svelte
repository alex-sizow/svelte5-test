<script>
	let count = $state(0);
</script>

<section>
	<h1>Main</h1>
	<div class="count">
		<input type="text" bind:value={count} />
		<p>{count}</p>
		<button onclick={() => count++}>count+</button>
	</div>
</section>

<style scoped>
	section {
		display: flex;
		flex-direction: column;
		margin-top: 50px;
		color: white;
	}
	h1 {
		margin: 0 auto;
		position: relative;

		display: block;
		font-size: 30px;
		color: aliceblue;
	}

	.count {
		display: flex;
		justify-content: center;
		flex-direction: column;
		margin: 50px auto;
		font-size: 20px;
		width: 200px;
		height: 160px;
		gap: 15px;

		> input {
			width: 200px;
			height: 90px;
			padding: 0 10px;
			font-size: 20px;
			color: black;
			border-radius: 10px;
		}

		> p {
			text-align: center;
			font-size: 50px;
			font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
		}

		button {
			background-color: red;
			font-size: 40px;
			border-radius: 20px;
		}
	}
</style>
