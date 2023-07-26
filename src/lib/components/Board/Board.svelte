<script>
	import Cell from './Cell.svelte';
    import {fly} from 'svelte/transition';
	import {flip} from 'svelte/animate';

	// Define los números iniciales del Sudoku
    let numbers = Array.from({length: 81}, (_, index) => index + 1)
	.map(number => ({number}));

	// Define el tamaño del Sudoku (9x9)
	function shuffle() { 
		numbers = numbers.sort(() => .5 - Math.random())
	}
	function remove() { 
		numbers = numbers.slice(1)
	}

    let value;
</script>

<button on:click={shuffle}>
	shuffle
</button>
<button on:click={remove}>
	remove
</button>
<div class="max-w-2xl mx-auto">
    <div class="board">
        {#each numbers as numberObject (numberObject)}
			<div class="cell" out:fly={{x: -500, duration: 5000}} animate:flip>{numberObject.number}</div>
		{/each}
    </div>
</div>

<style>
.board {
	/* display: flex; */
	display: grid;
	gap: 0.5rem;
		/* grid-template-columns: repeat(9, 1fr); 9 columnas */
		grid-auto-rows: minmax(min(4rem, 100%), 1fr);
		grid-template-columns: repeat(11, 1fr);
		/* grid-template-columns: repeat(9, minmax(min(4rem, 100%), 1fr));  */
		/* grid-template-columns: repeat(2, 1fr) repeat(2, 1fr); */
		grid-auto-flow: dense;
	/* flex-wrap: wrap; */
	/* width: 220px; */
}
/* .cell {
	text-align: center;
	line-height: 25px;
	width: 25px;
	height: 25px;
	border: 1px solid #aaa;
	margin-right: -1px;
	margin-bottom: -1px;
} */
.cell {
        /* width: 3rem;
        height: 3rem; */
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 2.5rem; /* Ajusta el tamaño del texto según el tamaño de la celda */
        border: 1px solid #cfc2c2;
    }
.cell:nth-child(3n), .cell:nth-child(6n) {
	/* margin-right: 5; */
	border: 1px solid #cfc2c2;
	grid-column-end: span 2; /* Ocupa el espacio de dos columnas */
	margin-right: 53%; /* Padding de 0.5rem multiplicado por 5 (mitad de 11 columnas) */
}
.cell:nth-child(9n) {
	border: 1px solid #cfc2c2;
	grid-column-end: span 1; /* Ocupa el espacio de dos columnas */
	margin-right: 0px;
}
.cell:nth-child(27n) {
	margin-bottom: 0;
}
</style>
