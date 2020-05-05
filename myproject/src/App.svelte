<script>
	let name = 'Damindu Sandaruwan Bandara';
	let degree = 'Red';
	let education='Undergraduate in University of Sri Jayewardhanapura';
	const handlecolor = () => {
		degree = 'BICT';
	};
	const degreeInput = (e) => {
		degree = e.target.value;
	}
</script>

<main>
	<h1>Hi!</h1>
	<h1>{name}!</h1>
	<h3>{education}</h3>
	<h3>{degree}</h3>
	<button on:click={handlecolor}>Update Degree</button>
	<input type="text" on:input={degreeInput}>
	
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