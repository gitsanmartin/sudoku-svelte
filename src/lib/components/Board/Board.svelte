<script>
	import Cell from './Cell.svelte';
	import { fly } from 'svelte/transition';
	import { flip } from 'svelte/animate';

	// Define los números iniciales del Sudoku
	let numbers = Array.from({ length: 81 }, (_, index) => index + 1).map((number) => ({ number }));

	// Define el tamaño del Sudoku (9x9)
	function shuffle() {
		numbers = numbers.sort(() => 0.5 - Math.random());
	}
	function remove() {
		numbers = numbers.slice(1);
	}

	let number;
</script>

<button on:click={shuffle}> shuffle </button>
<button on:click={remove}> remove </button>
<div class="max-w-2xl mx-auto">
	<div class="board max-w-md">
		{#each numbers as numberObject (numberObject)}
			<div class="cell" out:fly={{ x: -500, duration: 5000 }} animate:flip>
				{numberObject.number}
			</div>
		{/each}
	</div>
</div>

<style>
	.board {
		display: grid;
		gap: 0.1rem;
		grid-auto-rows: minmax(min(0.2rem, 100%), 0.3fr);
		grid-template-columns: repeat(9, 0.2fr);
		/* grid-template-columns: repeat(22, 0.2fr); */
		grid-auto-flow: dense;
	}

	.cell {
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 1.5rem;
		border: 1px solid #cfc2c2;
		/* grid-column-end: span 2; */
		/* grid-row-end: span 2; */
	}
	.cell:nth-child(3n), .cell:nth-child(6n), .cell:nth-child(9n) {
		/* border: 1px solid #cfc2c2; */
		/* grid-column-end: span 3;
		margin-right: 36%; */
	}
	.cell:nth-child(n + 19):nth-child(-n + 27)
	/* .cell:nth-child(n + 46):nth-child(-n + 54) */
	{
		/* grid-row-end: span 3;
		margin-bottom: calc(0.5rem * 5);  */
		/* Padding de 0.5rem multiplicado por 5 (mitad de 11 filas) */
	}
</style>
