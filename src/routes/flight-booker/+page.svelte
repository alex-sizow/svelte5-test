<script>
	import { onMount } from 'svelte';

	let flightType = 'one-way';
	let startDate = '';
	let returnDate = '';
	let isReturnDisabled = true;

	onMount(() => {
		startDate = new Date().toISOString().split('T')[0];
	});

	function handleFlightTypeChange(event) {
		flightType = event.target.value;
		isReturnDisabled = flightType === 'one-way';
		if (isReturnDisabled) {
			returnDate = '';
		}
	}
</script>

<h1>Flight Booker</h1>
<section>
	<label>
		<span>Flight Type:</span>
		<select bind:value={flightType} on:change={handleFlightTypeChange}>
			<option value="one-way">One-way</option>
			<option value="round-trip">Round-trip</option>
		</select>
	</label>

	<label>
		<span>Start Date:</span>
		<input type="date" bind:value={startDate} />
	</label>

	<label>
		<span>Return Date:</span>
		<input type="date" bind:value={returnDate} disabled={isReturnDisabled} />
	</label>
</section>

<style>
	h1 {
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
		padding: 0.5rem;
		font-size: 1rem;
	}
</style>
