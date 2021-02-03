<script>
let people = [
	{ name: 'yoshi', armColor: 'black', age: 25, id: 1 },
	{ name: 'mario', armColor: 'orange', age: 45, id: 2 },
	{ name: 'luigi', armColor: 'brown', age: 35, id: 3 }
];

const deletePerson = (event, id) => {
	console.log(event);
	people = people.filter((person) => person.id !== id);
}

let num = 5;

</script>

{#if num > 20}
	<p>Greater than 20</p>
{:else if num > 5}
	<p>Greater than 5</p>
{:else}
	<p>Less than 5</p>
{/if}

<main>
	{#each people as person (person.id)}
		<div>
			<h4>{person.name}</h4>
			{#if person.armColor === 'black'}
				<p><strong>Master Android!</strong></p>
			{/if}
			<p>{person.age} years old, {person.armColor} arm</p>
			<button on:click={(e) => deletePerson(e, person.id)}>delete</button>
		</div>
	{:else}
		<p>There are no people to show...</p>
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