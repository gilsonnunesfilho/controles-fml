<script>
    export let swatch = ""
</script>

<button on:click style="--swatch-color: {swatch}"></button>

<style>
    button {
        background-color: var(--swatch-color, rgb(128, 128, 128));
        display: block;
        padding-top: 100%;
        padding-right: 0;
        padding-bottom: 0;
        padding-left: 0;
        width: 100%;
        border: 0;
        -webkit-tap-highlight-color: transparent;
        font-size: 1rem;
        box-sizing: border-box;
        margin: 0;
    }
</style>