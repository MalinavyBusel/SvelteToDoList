<script>
	import ToDoInputForm from "./ToDoInputForm.svelte";
	import ToDoList from "./ToDoList.svelte";
	let nameEntered = false

	let firstName = ""
	let lastName = ""

	$: fullname = firstName + " " + lastName 

	function handleSubmit() {
		if (firstName && lastName) {
			nameEntered = true
		}
	}
</script>

<main>
{#if nameEntered} 
	<h1>Welcome to task manager, {fullname}</h1>
	<ToDoInputForm userName={fullname}/>
	<ToDoList />
{:else}
	<form on:submit|preventDefault={handleSubmit}>
		<h1>Welcome to task manager!</h1>
		<h3>Please enter your name:</h3>
		<div>
			<input bind:value={firstName} type="text" placeholder="First name" required>
		</div>
		<div>
			<input bind:value={lastName} type="text" placeholder="Last name" required>
		</div>
		<button on:click={handleSubmit}>Start managing tasks</button>
	</form>
{/if}
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}
</style>