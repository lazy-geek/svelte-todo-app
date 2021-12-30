<script>
    import { createEventDispatcher } from "svelte";

    import trashIcon from "../assets/trash.svg";

    export let id;
    const dispatch = createEventDispatcher();

    function submit() {
        dispatch("delete", { id: id });
    }
</script>

<button class="delete" on:click={submit}>
    <img src={trashIcon} alt="Delete" width="18" height="18" />
</button>

<style>
    .delete {
        padding: 10px 20px;
        margin-left: 5px;
        color: white;
        background-color: #ff1744;
        border-radius: 5px;
    }
    .delete:hover {
        background-color: #e62b50;
    }
</style>
