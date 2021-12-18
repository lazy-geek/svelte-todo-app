<script>
    import { createEventDispatcher } from "svelte";

    export let id;
    const dispatch = createEventDispatcher();

    function submit() {
        dispatch("delete", { id: id });
    }
</script>

<button class="delete" on:click={submit}>Delete</button>

<style>
    .delete {
        padding: 10px 20px;
        margin-left: 5px;
        font-size: 16px;
        font-weight: bold;
        color: white;
        background-color: #f44336;
        border-radius: 5px;
    }
    .delete:hover {
        background-color: rgb(212, 61, 61);
    }
</style>
