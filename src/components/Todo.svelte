<script>
    import {createEventDispatcher} from 'svelte';

    const dispatch = createEventDispatcher();

    let checked = false;
    const onDelete = () => {
        dispatch('remove')
    }
</script>

<li class="todo-row" class:done={checked}>
    <input type="checkbox" bind:checked={checked}><span><slot/></span>
    <button on:click={onDelete} name="delete-btn" class="delete-btn">X</button>
</li>

<style>
    .todo-row {
        list-style: none;
        text-align: start;
        padding: .4em;
        margin-top: .5em;
        border: 1px black solid;
        border-radius: 5px;
        width: 100%;
        background-color: black;
        color: white;
        display: flex;
    }

    .delete-btn {
        margin-left: auto;
    }

    input[type=checkbox] {
        margin: 0;
        padding: 0;

    }

    .done {
        text-decoration: line-through;
    }

    span {
        padding-left: 4px;
    }
</style>
