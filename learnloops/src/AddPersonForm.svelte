<script>

    import {createEventDispatcher} from 'svelte';

    let dispatch = createEventDispatcher();

    let name;
    let favColour;
    let age;
    // let soft =false;
    // let net =false;
    // let mul =false;

    let skills=[];

    const handleSubmit=()=>{
        
        const person = {
            name,
            favColour,
            age,
            skills,
            id:Math.random()
        }
        dispatch('addPerson',person);

        console.log(name,favColour,age);
        // console.log(soft,net,mul);
        console.log(skills);

    }
</script>

<form on:submit|preventDefault={handleSubmit}>
    <h3>Add Person</h3>
    <input type="text" placeholder="name" bind:value={name}>
    <input type="text" placeholder="favourite color" bind:value={favColour}>
    <input type="number" placeholder="age" bind:value={age}>
    <label>Skills : </label>
    <!-- <input type="checkbox" bind:checked={soft}>Software<br>
    <input type="checkbox" bind:checked={net}>Networking <br>
    <input type="checkbox" bind:checked={mul}>Multimedia <br> -->

    <input type="checkbox" bind:group={skills} value="software">Software<br>
    <input type="checkbox" bind:group={skills} value="networking">Networking <br>
    <input type="checkbox" bind:group={skills} value="multimedia">Multimedia <br>
    
    <label>Select Color : </label>
    <select bind:value={favColour}>
        <option value="black">Black</option>
        <option value="orange">Orange</option>
        <option value="red">Red</option>
        <option value="blue">Blue</option>
    </select>

    <button>Add Person</button>
</form>

<style>

</style>