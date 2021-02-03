<script>
	let firstName = 'Pabs';
	let lastName = 'Kinator';
	let armColor = 'Black'

	// reactive values
	$: fullName = `${firstName} ${lastName}`;

	// reactive statement
	$: {
		console.log(armColor);
		console.log(fullName);
	}

	const handleClick = () => {
		armColor = 'pink';
	};

	const handleInput = (e) => {
		armColor = e.target.value;
	};
</script>

<main>
	<p style="color: {armColor}">{fullName} - {armColor} arm</p>

	<input type="text" bind:value={firstName}>
	<input type="text" bind:value={lastName}>
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