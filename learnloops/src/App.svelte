<script>

	import Offer from './modal.svelte';
	import AddPersonForm from './AddPersonForm.svelte';

	let showModal = false;

	const toggleModal = () => {
		showModal= !showModal;
	}

	let people =[
		{name: 'Damindu', favColour:'black', age:25, id:1},
		{name: 'Sandaruwan', favColour:'red',age:23, id:2},
		{name: 'Bandara', favColour:'blue', age:22, id:3}
	];

	const handleclick = (e,id) => {
		// delete the person from people
		console.log(id); 
		people=people.filter((person)=>person.id != id);
		console.log(e);

	}

	const addPerson=(e)=>{
		console.log(e.detail);

		const person = e.detail;
		people=[person, ...people];
		showModal=false;
	}

</script>

<Offer message="Hey, I am prop value" isPromo={true} {showModal} on:click={toggleModal}>
	<!-- <h3>Add a New Person</h3>
	<form>
		<input type="text" placeholder="name">
		<input type="text" placeholder="favourite color">
		<button>Add Person</button>
	</form> -->
	<!-- <div slot="title">
		<h3>Add a New Person</h3>
	</div> -->

	<AddPersonForm on:addPerson={addPerson}/>
</Offer>

<main>

	<button on:click={toggleModal}>Open Modal</button>

	<h1>Loops</h1>
	{#each people as person (person.id)}
		<div>
			<h4>Hi ... {person.name} .</h4>
			{#if person.favColour === 'black'}
				<p><strong>MASTER black</strong></p>			
			{/if}
			<p>{person.age} years old. {person.favColour} is favourite colour.</p>
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