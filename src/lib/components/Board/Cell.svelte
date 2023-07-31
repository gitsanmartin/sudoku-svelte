<script>
    import { fly } from 'svelte/transition';
    import { flip } from 'svelte/animate';

    export let number;
    export let columnGap;
</script>

<!-- <div class="cell" use:fly={{ x: -500, duration: 5000 }}>
    {number}
</div> -->
{number}
