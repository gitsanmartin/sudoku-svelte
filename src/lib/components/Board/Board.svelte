<script>
	import Cell from './Cell.svelte';

	// Define los números iniciales del Sudoku
    const initialNumbers = [
        [5, 3, 0, 0, 7, 0, 0, 0, 0],
        [6, 0, 0, 1, 9, 5, 0, 0, 0],
        [0, 9, 8, 0, 0, 0, 0, 6, 0],
        [8, 0, 0, 0, 6, 0, 0, 0, 3],
        [4, 0, 0, 8, 0, 3, 0, 0, 1],
        [7, 0, 0, 0, 2, 0, 0, 0, 6],
        [0, 6, 0, 0, 0, 0, 2, 8, 0],
        [0, 0, 0, 4, 1, 9, 0, 0, 5],
        [0, 0, 0, 0, 8, 0, 0, 7, 9]
    ];

	// Define el tamaño del Sudoku (9x9)
	const size = initialNumbers.length;

    let value;
</script>
<h1>{size}</h1>
<div class="max-w-2xl mx-auto">
    <div class="board">
        {#each initialNumbers as row, rowIndex}
            {#each row as value, colIndex}
                <!-- <Cell {value} isGroupOf3={(colIndex + 1) % 3 === 0}/> -->
                <Cell {value}/>
            {/each}
        {/each}
    </div>
</div>

<style>
    .board {
		display: grid;
		gap: 0.5rem;
		/* grid-template-columns: repeat(9, 1fr); 9 columnas */
		grid-auto-rows: minmax(min(4rem, 100%), 1fr);
		grid-template-columns: repeat(9, minmax(min(4rem, 100%), 1fr)); 
		grid-auto-flow: dense;
		/*  auto-fill: expande las columnas para ocupar el lugar
            auto-fit: no expande las columnas y genera columnas vacias para ocupar el lugar */
        /* max-width: 400px; */
	}
</style>
