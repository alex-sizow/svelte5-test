<script>
	import { text } from '@sveltejs/kit';

	let todos = $state([
		{ text: 'Eat bread!', done: true },
		{ text: 'Drink milk!', done: false },
		{ text: 'Not eat!!!!', done: false }
	]);
	const addTodo = (event) => {
		if (event.key !== 'Enter') {
			return;
		}

		const todoText = event.target.value;
		const id = window.crypto.randomUUID('dfgdg');

		const todo = { text: todoText, done: false };

		todos = [todo, ...todos];
	};
</script>

<ul class="todos">
	<li>
		<input onkeydown={addTodo} class="todos__item" type="text" placeholder="Add todo..." />
	</li>
	{#each todos as todo, i}
		<li class="todos__item">
			<input value={todo.text} type="text" />
			<input value={todo.done} type="checkbox" />
		</li>
	{/each}
</ul>
