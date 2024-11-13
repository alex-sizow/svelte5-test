<script lang="ts">
	let selected = $state('one-way');

	const getDate = () => {
		const date = new Date();
		const [month, day, year] = date
			.toLocaleDateString('fr-FR', {
				year: 'numeric',
				month: '2-digit',
				day: '2-digit'
			})
			.split('/');

		return `${year}-${month}-${day}`;
	};

	let startDate = $state(getDate());
	let returnDate = $state(getDate());

	const handleSubmit = (e) => {};
</script>

<form onsubmit={handleSubmit}>
	<h1>Flight Booker</h1>
	<section>
		<label>
			<span>Flight Type:</span>
			<select bind:value={selected} required>
				<option value="one-way">One-way</option>
				<option value="round-trip">Round-trip</option>
			</select>
		</label>

		<label>
			<span>Start Date:</span>
			<input type="date" bind:value={startDate} min={getDate()} required />
		</label>

		<label>
			<span>Return Date:</span>
			<input
				type="date"
				bind:value={returnDate}
				min={getDate()}
				disabled={!startDate || (selected === 'return' && returnDate < startDate)}
				required
			/>
		</label>
	</section>

	<button type="submit">Book</button>
</form>

<style>
	h1 {
		margin: 20px;
		text-align: center;
		font-size: 2rem;
		margin-bottom: 1rem;
	}

	section {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 1rem;
	}

	label {
		display: flex;
		flex-direction: column;
		align-items: flex-start;
	}

	span {
		margin-bottom: 0.5rem;
	}

	input,
	select {
		border-radius: 20px;
		padding: 0.8rem;
		font-size: 1rem;
		color: black;
	}

	input[disabled] {
		border: 4px solid red;
	}
	button {
		display: flex;
		margin: 20px auto;
		border: 2px solid aqua;
		border-radius: 15px;
		padding: 10px 18px;
		font-size: 20px;
	}
</style>
