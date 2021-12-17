<script>
    import { createEventDispatcher } from "svelte";

    let value = "";
    const dispatch = createEventDispatcher();

    function submit() {
        dispatch("submit", { text: value });
    }
</script>

<form>
    <input
        type="text"
        name="task"
        id="task"
        placeholder="type something"
        bind:value
    />
    <button type="submit" id="submit" on:click={submit}>Submit</button>
</form>

<style>
    form {
        display: flex;
    }
    #task {
        display: inline-block;
        padding: 10px;
        outline: none;
        padding: 7px;
        width: 100%;
        border: 1px solid grey;
        background-color: white;
    }
    #submit {
        padding: 7px 20px;
        margin-left: 5px;
        font-size: 16px;
        font-weight: bold;
        color: white;
        background-color: blueviolet;
        border-radius: 5px;
    }
    #submit:hover {
        background-color: rgb(120, 35, 201);
    }
</style>
