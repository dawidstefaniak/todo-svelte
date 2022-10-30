<script lang="ts">
    import Todo from "./Todo.svelte";

    let text = "";
    let todos = [];
    let submit = () => {
        todos.push(text);
        text = "";
        todos = todos;
    };

</script>

<div id="todos-wrapper">
    <form on:submit|preventDefault={submit}>
        <input type="text" name="text-todo" bind:value={text}/>
    </form>
    <ul>
        {#each todos as todo}
            <Todo><span>{todo}</span></Todo>
        {/each}
    </ul>
</div>

<style>
    #todos-wrapper {
        margin-top: 300px;
        width: 400px;
        padding: 12px;
        margin-bottom: 12px;
        border-radius: 12px;
        border: 1px black solid;
    }
</style>
