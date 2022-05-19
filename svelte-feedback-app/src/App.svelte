<script>
	let firstName = 'Tommy'
	let lastName = 'Gun'
	let color = 'blue'
	let hideLink = false
	let userList = [
		{
			id:'1',
			name:'Akshat'
		},
		{
			id:'2',
			name:'Sabavat'
		},
		{
			id:'3',
			name:'Tanish'
		},
		{
			id:'4',
			name:'Kumar'
		}
	]

	const toggleColor = () => {
		color = color == 'blue' ? 'purple' : 'blue';
		hideLink = true
		userList = [...userList,{id:'5', name:'Jenny'}]
	}

	$:name = firstName + ' ' + lastName
</script>

<main>
	<h1 style="color: {color};">Hello {name}!</h1>
	<!--The if block below conditionally renders the component based on the value returned by the javascript function-->
	{#if hideLink}
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	{:else}
	<p>Click button to show link</p>
	{/if}
	<button on:click={toggleColor}>Click Me</button>
	{#each userList as users (users.id) }
		<h4>{users.id}. {users.name}</h4>
	{/each}
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