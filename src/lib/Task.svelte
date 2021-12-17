<script>
    export let isChecked = false;
    export let content = "";
    export let id;

    function toggle() {
        isChecked = !isChecked;
    }
</script>

<div class="task" on:click={toggle}>
    <input type="checkbox" name={id} bind:checked={isChecked} />
    <label for={id} class="content">{content}</label>
</div>

<style>
    .task {
        cursor: pointer;
        padding: 10px;
        border: 1px solid grey;
        border-radius: 4px;
        display: flex;
        align-items: center;
    }
    .content {
        cursor: pointer;
        pointer-events: none;
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
