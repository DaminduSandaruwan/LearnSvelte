<script>
	let firstname = 'Damindu';
	let lastname = 'Sandaruwan';
	let color = 'Red';

	$: fullname=`${firstname} ${lastname}`
	$: {
		console.log(fullname);
		console.log(color);
	}

	let education='Undergraduate in University of Sri Jayewardhanapura';
	const handlecolor = () => {
		color = 'Black';
	};
	const colorInput  = (e) => {
		color = e.target.value;
	}
</script>

<main>
	<h1>Hi</h1>
	<p>{fullname} - {color} Color</p>
	<input type="text" bind:value={firstname}>
	<input type="text" bind:value={lastname}>
	<input type="text" bind:value={color}>
	
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