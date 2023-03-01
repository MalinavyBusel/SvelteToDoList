<script>
    import {toDoItems} from "./store.js"
    export let userName;
    let newitem = ""

    function addToList() {
        $toDoItems = [$toDoItems, {text: newitem, status: false}]
        newitem = ""
    }
</script>

<input bind:value={newitem} type="text" placeholder="Add a new task">
<button on:click={addToList}>Add</button>


<h3>{userName}'s task list:</h3>
