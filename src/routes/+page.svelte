<script>
	import { text } from '@sveltejs/kit';

	let todos = $state([
		{ text: 'Eat bread!', done: false },
		{ text: 'Drink milk!', done: false },
		{ text: 'Not eat!!!!', done: false }
	]);
	let filter = $state('all');

	const addTodo = (event) => {
		if (event.key !== 'Enter') {
			return;
		}

		const todoText = event.target.value;
		const id = window.crypto.randomUUID('dfgdg');

		const todo = { text: todoText, done: false };

		todos = [...todos, todo];

		event.target.value = '';
	};

	const editTodo = (event) => {
		const todoEl = event.target;
		const index = todoEl.dataset.index;
		todos[index].text = todoEl.value;
	};

	const toggleTodo = (event) => {
		const todoEl = event.target;
		const index = todoEl.dataset.index;
		todos[index].done = !todos[index].done;
	};

	const setFilter = (type) => {
		filter = type;
	};

	const filterTodos = () => {
		switch (filter) {
			case 'all':
				return todos;
			case 'done':
				return todos.filter((todo) => todo.done);
			case 'in work':
				return todos.filter((todo) => todo.done === false);
			default:
				console.warn(`Unknown filter type: ${filter}`);
				return todos;
		}
	};

	let filteredTodos = $derived(filterTodos());
</script>

<ul class="todos">
	{#each filteredTodos as todo, i}
		<li class="todos__item">
			<input oninput={editTodo} data-index={i} value={todo.text} type="text" />
			<input
				checked={todo.done}
				onchange={toggleTodo}
				data-index={i}
				value={todo.done}
				type="checkbox"
			/>
		</li>
	{/each}
	<li>
		<input onkeydown={addTodo} class="todos__item" type="text" placeholder="Add todo..." />
	</li>

	<div class="todos__filter">
		<button onclick={() => setFilter('all')} class="todos__filter_button">All</button>
		<button onclick={() => setFilter('done')} class="todos__filter_button">Done</button>
		<button onclick={() => setFilter('in work')} class="todos__filter_button">In work</button>
	</div>
</ul>
