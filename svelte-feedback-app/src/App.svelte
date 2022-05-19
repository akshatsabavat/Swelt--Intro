<script>
	let firstName = 'Tommy'
	let lastName = 'Gun'
	let color = 'blue'
	let tempNumber = 1000

	function colorChange(numberHold){
		console.log(numberHold);
	}

	$:name = firstName + ' ' + lastName
</script>

<main>
	<h1 style="color: {color};">Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<button on:click={() => colorChange(tempNumber)}>Click Me</button>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>