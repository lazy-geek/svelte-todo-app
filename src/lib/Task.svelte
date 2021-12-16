<script>
    export let isChecked = false;
    export let content = '';
    export let id;
</script>

<div class='task'>
    <input type="checkbox" name={id} id={id} bind:checked={isChecked}>
    <label for={id} class="content">{content}</label>
</div>

<style>
    .task{
        padding: 10px;
        border: 1px solid grey;
        border-radius: 4px;
        box-sizing: content-box;
        display: flex;
        align-items: center;
    }
    .content{
        display: inline-block;
        margin-left: 4px;
    }

    input[type='checkbox']:checked + .content{
        text-decoration: line-through;
        color: grey;
    }
</style>