<script>
    import {toDoItems} from "./store.js"
    import {onMount} from "svelte"
    export let userName;
    let newitem = ""
    let newItemInputForm = null

    onMount(() => {newItemInputForm.focus()})

    function addToList() {
        $toDoItems = [...$toDoItems, {text: newitem, status: false}]
        newitem = ""
    }
</script>

<input bind:value={newitem} bind:this={newItemInputForm} type="text" placeholder="Add a new task">
<button on:click={addToList}>Add</button>


<h3>{userName}'s task list:</h3>
