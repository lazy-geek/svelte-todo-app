<script>
import Task from './lib/Task.svelte';
let tasks = [
	{'content': 'Task 1', 'isCheked': false},
	{'content': 'Task 2', 'isCheked': false},
	{'content': 'Task 3', 'isCheked': false},
	{'content': 'Task 4', 'isCheked': false}
	];

	function addTask(e) {
		tasks = [...tasks,{'content':e.detail.text,'isCheked':false}];
	}
</script>

<main>
	<h1>Todo List</h1>
	{#each tasks as task , i }
	<Task content={task.content} bind:isChecked = {task.isChecked} id={i}/>
	{/each}

</main>

<style>
	main{
		min-width: 400px;
		padding: 40px;
		background-color: white;
		display: grid;
		grid-template-columns: 1fr;
		row-gap: 20px;
	}
</style>
