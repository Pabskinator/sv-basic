<script>
	let name = 'Pabs';
	let armColor = 'Black'

	const handleClick = () => {
		armColor = 'pink';
	};

	const handleInput = (e) => {
		armColor = e.target.value;
	};
</script>

<main>
	<h1>Hello {name}!</h1>
	<p style="color: {armColor}">{armColor} arm</p>

	<button on:click={handleClick}>Update arm color</button>
<!--	<input type="text" on:input={handleInput} value="{armColor}">-->
	<input type="text" bind:value={armColor}>
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