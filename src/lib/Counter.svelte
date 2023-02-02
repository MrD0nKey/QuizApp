<script lang="ts">
    import { fade } from 'svelte/transition';
    let count: number = 0;
    let visible: boolean = true;
    const increment = () => {
        count += 1;
    };

    const incrementMinus = () => {
        if (count > 0) {
            count -= 1;
        }
    };

    const handleFade = () => {
        visible = !visible; 
    }
</script>
<button style="margin-bottom: 1em;" on:click={handleFade}>Click to fade out or fade in!</button>
{#if visible}
    <div transition:fade>
        <button on:click={increment}>
            count was {count}
        </button>
        <button on:click={incrementMinus}> Decrement the count ! </button>
        <br />
        <button>Allo</button>
    </div>
{/if}

<style>
    div {
        width: 500px;
        display: flex;
        flex-flow: column;
        border: 3px solid blue;
        border-radius: 20px;
    }

    div button {
        margin: 1em auto;
        width: 60%;
    }
</style>
