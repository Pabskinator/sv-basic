<script>
import Modal from './Modal.svelte';
import AddPersonForm from './addPersonForm.svelte';

let showModal = false;
let people = [
	{ name: 'yoshi', armColor: 'black', age: 25, id: 1, skills: ['eating'] },
	{ name: 'mario', armColor: 'orange', age: 45, id: 2, skills: ['walking'] },
	{ name: 'luigi', armColor: 'brown', age: 35, id: 3, skills: ['seeing'] }
];

const deletePerson = (event, id) => {
	console.log(event);
	people = people.filter((person) => person.id !== id);
}

const toggleModal = () => {
	showModal = !showModal;
}

const addPerson = (e) => {
	const person = e.detail
	people = [person, ...people];
	showModal = false;
}

let num = 5;

</script>

<Modal {showModal} on:click={toggleModal}>
	<AddPersonForm on:addPerson={addPerson} />
</Modal>

<main>
	<button on:click={toggleModal}>Open Modal</button>

	{#each people as person (person.id)}
		<div>
			<h4>{person.name}</h4>
			{#if person.armColor === 'black'}
				<p><strong>Master Android!</strong></p>
			{/if}
			<p>{person.age} years old, {person.armColor} arm</p>
			<label>Skills:</label>
			{#each person.skills as skill}
				<div>{skill}</div>
			{/each}
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

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>