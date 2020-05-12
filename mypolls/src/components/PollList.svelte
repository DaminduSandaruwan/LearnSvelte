<script>
    // import {onMount, onDestroy} from 'svelte';
    import PollStore from '../stores/PollStore.js';
    import PollDetails from './PollDetails.svelte';
    import {fade,slide,scale} from 'svelte/transition';

    // export let polls = [];

    // const unsub = PollStore.subscribe((data)=>{
    //     polls = data;
    // });

    // onMount(()=>{
    //     //maybe get data from a db
    //     console.log('component mounted');
    // });

    // onDestroy(()=>{
    //     //unsub from store
    //     console.log('component destroy');
    //     unsub();
    // });
    
</script>

<div class="poll-list">
    {#each $PollStore as poll (poll.id)}
        <!-- <div>{poll.question}</div> -->
        <!-- <PollDetails {poll} on:vote/> -->

        <!-- <div transition:fade> -->
        <!-- <div in:fade> -->
        <!-- <div in:fade out:scale> -->
        <!-- <div in:fade out:slide> -->
        <div in:fade out:scale|local>
            <PollDetails {poll}/>
        </div>
    {/each}
 </div>

 <style>
    .poll-list{
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-gap: 20px;
         
    }
 </style>