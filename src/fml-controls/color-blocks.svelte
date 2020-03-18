<script>
    import ColorBlock from './color-block.svelte'
    import TinyColor from '@ctrl/tinycolor'

    export let selectedColor = ""
    
    $: isLight = new TinyColor(selectedColor).isLight()

    let colorSwatches = [
        "#EB5757",
        "#F2994A",
        "#F2C94C",
        "#219653",
        "#27AE60",
        "#6FCF97",
        "#2F80ED",
        "#56CCF2",
        "#9B51E0",
        "#BB6BD9"
    ]

    function setColor(color) {
        selectedColor = color
    }
</script>

<ul class="color-blocks">
    {#each colorSwatches as swatch}
    <li class="color-block">
        <ColorBlock bind:swatch on:click={() => setColor(swatch)} />
    </li>
    {/each}
    <li class="picker">
        <label class="picker-label" class:is-light={isLight}>
            <i class="material-icons">colorize</i>
            <input type="color" bind:value={selectedColor}>
        </label>
    </li>
    <li class="type-color">
        <input size="1" bind:value={selectedColor} type="text">
    </li>
</ul>

<style>
    input[type="color"] {
        -webkit-appearance: none;
        border: none;
    }

    input[type="color"]::-webkit-color-swatch-wrapper {
        padding: 0;
    }

    input[type="color"]::-webkit-color-swatch {
        border: none;
    }

    .color-blocks {
        list-style: none;
        display: grid;
        grid-gap: .5rem;
        grid-template-columns: repeat( auto-fit, minmax(2rem, 1fr) );
        grid-auto-rows: minmax(2rem, 1fr);
        padding: .5rem 1rem;
        margin: 0;
    }

    .color-block {
        border-radius: .125rem;
    }

    .picker {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .picker-label {
        position: relative;
        width: 100%;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .picker-label > i {
        position: absolute;
        color: black;
    }

    .picker-label.is-light > i {
        position: absolute;
        color: white;
    }

    .picker-label > input {
        width: 100%;
        height: 100%;
        padding: 0;
        box-sizing: border-box;
        margin: 0;
        border-radius: .125rem;
    }

    .type-color {
        grid-column: span 3;
    }

    .type-color input {
        height: 100%;
        width: 100%;
        font-size: 1rem;
        padding: 0 .5rem;
        box-sizing: border-box;
        border: 1px solid rgb(128,128,128);
        border-radius: .125rem;
        background-color: transparent;
    }

</style>