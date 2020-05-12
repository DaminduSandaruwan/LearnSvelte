<script>
    import PollStore from '../stores/PollStore.js';
    import PollDetails from './PollDetails.svelte';
    export let polls = [];
    PollStore.subscribe((data)=>{
        polls = data;
    });
    
</script>

<div class="poll-list">
    {#each polls as poll (poll.id)}
        <!-- <div>{poll.question}</div> -->
        <PollDetails {poll} on:vote/>
    {/each}
 </div>

 <style>
    .poll-list{
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-gap: 20px;
         
    }
 </style>