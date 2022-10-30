<script>
    let checked = false;
</script>

<li class="todo-row" class:done={checked}> 
    <input type="checkbox"  bind:checked={checked}><span><slot  /></span>
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
