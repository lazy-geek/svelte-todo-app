<script>
    export let isChecked = false;
    export let content = "";
    export let id;

    import { createEventDispatcher } from "svelte";
    const dispatch = createEventDispatcher();
    function toggle() {
        isChecked = !isChecked;
        dispatch("toggle", { id: id });
    }
</script>

<div class="task" on:click={toggle} class:checked={isChecked}>
    <input type="checkbox" name={id} bind:checked={isChecked} aria-label="done"/>
    <label for={id} class="content">{content}</label>
</div>

<style>
    .task {
        cursor: pointer;
        width: 100%;
        padding: 10px;
        border: 1px solid grey;
        border-radius: 4px;
        display: flex;
        align-items: center;
    }
    .checked {
        opacity: 0.6;
    }
    .content {
        cursor: pointer;
        pointer-events: none;
        word-break: break-all;
        display: inline-block;
        margin-left: 4px;
    }
    input[type="checkbox"] {
        pointer-events: none;
        cursor: pointer;
    }
    input[type="checkbox"]:checked + .content {
        text-decoration: line-through;
        color: grey;
    }

    
</style>
