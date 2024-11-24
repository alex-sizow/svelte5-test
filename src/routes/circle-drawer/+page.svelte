<script lang="ts">
	type Circle = {
		id: string;
		cx: number;
		cy: number;
		r: number;
	};
	type Status = 'drawing' | 'editing';

	let status = $state<Status>('drawing');

	let circles = $state<Circle[]>([{ cx: 300, cy: 200, r: 40 }]);

  const drawCircle = () => {
    
  }
</script>

<div class="draw-container">
	<div class="draw-container__buttons">
		<button>Undo</button>
		<button>Redo</button>
	</div>

	<svg viewBox="0 0 600 500">
		{#each circles as circle}
			<circle {...circle} stroke="#fff" stroke-width="2"></circle>
		{/each}
	</svg>
</div>

<style scoped>
	.draw-container {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		gap: 20px;
		margin-top: 40px;

		.draw-container__buttons {
			display: flex;
			gap: 20px;
			font-size: 27px;
			font-weight: 600;

			button {
				padding: 7px 10px;
				border: 2px solid white;
				border-radius: 10px;
				transition: border 0.2s ease-in;
			}
			:hover {
				transition: border 0.2s ease-in;
				border: 2px solid red;
			}
		}
	}
	svg {
		width: 600px;
		height: 500px;
		border: 2px solid white;
		border-radius: 13px;
	}
</style>
