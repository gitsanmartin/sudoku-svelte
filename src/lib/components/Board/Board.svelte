<script>
	import Cell from './Cell.svelte';

	let board = [
		[0, 0, 0, 0, 0, 0, 0, 0, 0],
		[0, 0, 0, 0, 0, 0, 0, 0, 0],
		[0, 0, 0, 0, 0, 0, 0, 0, 0],
		[0, 0, 0, 0, 0, 0, 0, 0, 0],
		[0, 0, 0, 0, 0, 0, 0, 0, 0],
		[0, 0, 0, 0, 0, 0, 0, 0, 0],
		[0, 0, 0, 0, 0, 0, 0, 0, 0],
		[0, 0, 0, 0, 0, 0, 0, 0, 0],
		[0, 0, 0, 0, 0, 0, 0, 0, 0]
	];
</script>

<div class="board">
	{#each board as row, rowIndex}
		<div class="row" key={rowIndex}>
			{#each row as cell, cellIndex}
				<Cell value={cell} key={cellIndex} />
			{/each}
		</div>
	{/each}
</div>

<style>
	.board {
		display: grid;
		grid-template-columns: repeat(9, 1fr);
		grid-gap: 4px;
		background-color: #eee;
		padding: 4px;
	}

	.row {
		display: flex;
		align-items: center;
		justify-content: center;
	}
</style>
