<script>
	import AddTask from "./components/AddTask.svelte";
	import TaskList from "./components/TaskList.svelte";
	import { v4 as uuidv4 } from 'uuid';

	let tasks = [
		{id: uuidv4(), content: "Task 1", isCheked: false },
		{id: uuidv4(), content: "Task 2", isCheked: false },
		{id: uuidv4(), content: "Task 3", isCheked: false },
		{id: uuidv4(), content: "Task 4", isCheked: false },
	];

	function addTask(e) {
		tasks = [...tasks, {id: uuidv4(), content: e.detail.text, isCheked: false }];
	}
	function deleteTask(e){
		tasks = tasks.filter(({id}) => {
			return id != e.detail.id;
		});
	}
</script>

<main>
	<h1>Todo List</h1>
	<TaskList {tasks} on:delete={deleteTask}/>
	<AddTask on:submit={addTask} />
</main>

<style>
	main {
		min-width: 400px;
		padding: 40px;
		background-color: white;
		display: grid;
		grid-template-columns: 1fr;
		row-gap: 20px;
	}
</style>
