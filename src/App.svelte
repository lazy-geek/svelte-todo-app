<script>
	import AddTask from "./components/AddTask.svelte";
	import TaskList from "./components/TaskList.svelte";

	let tasks = [
		{ content: "Task 1", isCheked: false },
		{ content: "Task 2", isCheked: false },
		{ content: "Task 3", isCheked: false },
		{ content: "Task 4", isCheked: false },
	];

	function addTask(e) {
		tasks = [...tasks, { content: e.detail.text, isCheked: false }];
	}
	function deleteTask(e){
		tasks = tasks.filter(({content}) => {
			return content != tasks[e.detail.id].content;
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
