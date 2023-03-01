<script>
	import ToDoInputForm from "./ToDoInputForm.svelte";

	let firstName = "John"
	let lastName = "Doe"

	$: fullname = firstName + " " + lastName 
</script>

<main>
	<ToDoInputForm userName={fullname}/>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}
</style>