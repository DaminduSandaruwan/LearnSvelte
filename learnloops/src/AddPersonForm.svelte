<script>
    let name;
    let favColour;
    let age;

    const handleSubmit=()=>{
        console.log(name,favColour,age);
    }
</script>

<form on:submit|preventDefault={handleSubmit}>
    <h3>Add Person</h3>
    <input type="text" placeholder="name" bind:value={name}>
    <input type="text" placeholder="favourite color" bind:value={favColour}>
    <input type="number" placeholder="age" bind:value={age}>
    <button>Add Person</button>
</form>

<style>

</style>