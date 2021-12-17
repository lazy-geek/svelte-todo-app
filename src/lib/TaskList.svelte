<script>
    import Task from "./Task.svelte";
    export let tasks = [];
</script>

<div class="task-list">
    {#each tasks as task, i}
        <Task content={task.content} isChecked={task.isChecked} id={i} />
    {/each}
</div>

<style>
    .task-list {
        display: grid;
        grid-template-columns: 1fr;
        row-gap: 20px;
    }
</style>
