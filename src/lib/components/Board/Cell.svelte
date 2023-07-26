<script>
    export let value;
    export let columnGap;
</script>

<span class="cell">
    {value}
</span>

<!-- <span class="cell" style={columnGap ? 'margin-right: 1rem;' : ''}>
    {value}
</span> -->

<style>
    .cell {
        /* width: 3rem;
        height: 3rem; */
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 2.5rem; /* Ajusta el tamaño del texto según el tamaño de la celda */
        border: 1px solid #cfc2c2;
    }
</style>