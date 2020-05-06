<script>
	let people =[
		{name: 'Damindu', favcolor:'black', age:25, id:1},
		{name: 'Sandaruwan', favcolor:'red',age:23, id:2},
		{name: 'Bandara', favcolor:'blue', age:22, id:3}
	];
</script>

<main>
	<h1>Loops</h1>
	<div>
		<h4>{people[0].name}</h4>
		<p>{people[0].favcolor}</p>
	</div>
	<div>
		<h4>{people[1].name}</h4>
		<p>{people[1].favcolor}</p>
	</div>
	<div>
		<h4>{people[2].name}</h4>
		<p>{people[2].favcolor}</p>
	</div>
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