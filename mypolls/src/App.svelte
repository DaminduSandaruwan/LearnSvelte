<script>
	import Header from './components/Header.svelte';
	import Footer from './components/Footer.svelte';
	import Tabs from './shared/Tabs.svelte';
	import CreatePollForm from './components/CreatePollForm.svelte';

	//tabs
	let items = ['Current Polls', 'Add New Poll'];
	let activeItem = 'Current Polls';
	const tabChange = (e) =>{
		activeItem=e.detail;		
	}

</script>

<Header/>
<main>
	<Tabs {activeItem} {items} on:tabChange={tabChange}/>
	{#if activeItem==='Current Polls'}
		<p>Polls List component goes here....</p>
	{:else if activeItem==='Add New Poll'}
		<!-- <p>New Polls Form component goes here....</p> -->
		<CreatePollForm/>
	{/if}
</main>

<Footer/>
<style>
	main{
		max-width: 960px;
		margin: 40px auto;
	}
</style>