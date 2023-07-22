<script>
    export let value;
    export let isGroupOf3 = false;
</script>

<span class="cell">
    {value}
</span>

<style>
    .cell {
        width: 3rem; /* Ancho de cada celda */
        height: 3rem; /* Alto de cada celda */
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 2.5rem; /* Ajusta el tamaño del texto según el tamaño de la celda */
        border: 1px solid #cfc2c2;
    }
</style>