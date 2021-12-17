<script>
    import Task from "./Task.svelte";
    import Delete from "./Delete.svelte";
    export let tasks = [];
</script>

<div class="task-list">
    {#each tasks as task (task.id)}
    <div>
        <Task content={task.content} isChecked={task.isChecked} id={task.id} />
        <Delete id={task.id} on:delete/>
    </div>
    {/each}
</div>

<style>
    .task-list {
        display: grid;
        grid-template-columns: 1fr;
        row-gap: 20px;
    }
    div {
        display: flex;

    }
</style>
