<script>
    export let isChecked = false;
    export let content = '';
    export let id;
</script>

<div class='task'>
    <input type="checkbox" name={id} id={id} bind:checked={isChecked}>
    <label for={id} class="content">{content}</label>
</div>
