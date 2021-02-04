<script>
    let name;
    let armColor;
    let age;
    let skills = [];

    const handleSubmit = () => {
        console.log(name, armColor, age, skills);
    }
</script>

<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="name" bind:value={name}>
    <input type="number" placeholder="age" bind:value={age}>
    <label>Skills:</label>
    <input type="checkbox" bind:group={skills} value="fighting">fighting <br>
    <input type="checkbox" bind:group={skills} value="sneaking">sneaking <br>
    <input type="checkbox" bind:group={skills} value="running">running <br>
    <label>Arm Color:</label>
    <select bind:value={armColor}>
        <option value="black">black</option>
        <option value="red">red</option>
        <option value="yellow">yellow</option>
        <option value="orange">orange</option>
    </select>
    <button>Add Person</button>
</form>

<style>

</style>