<script>
	let people =[
		{name: 'Damindu', favcolor:'black', age:25, id:1},
		{name: 'Sandaruwan', favcolor:'red',age:23, id:2},
		{name: 'Bandara', favcolor:'blue', age:22, id:3}
	];

	const handleclick = (e,id) => {
		// delete the person from people
		console.log(id); 
		people=people.filter((person)=>person.id != id);
		console.log(e);

	}

</script>

<main>
	<h1>Loops</h1>
	{#each people as person (person.id)}
		<div>
			<h4>Hi ... {person.name} .</h4>
			<p>{person.age} years old. {person.favcolor} is favourite colour.</p>
			<button on:click={(e)=>{ 
				handleclick(e, person.id)
			}}>Delete</button>
		</div>
	{:else}
		<p>There are no people to show</p>
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