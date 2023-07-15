<script>
	import Board from '../lib/components/Board/Board.svelte';
</script>

<div class="container">
	<h1>Sudoku Game</h1>
	<Board />
</div>

<style>
	.container {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		height: 100vh;
	}
</style>