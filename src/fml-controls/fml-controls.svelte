<script>
    import FmlControl from './fml-control.svelte'

    let controls = [
        {
            title: "Fachada frente setor B",
            selectedColor: "#2F80ED",
            isOn: true
        },
        {
            title: "Estacionamento B13",
            selectedColor: "#EB5757",
            isOn: true
        },
        {
            title: "Estacionamento M6",
            selectedColor: "#56CCF2",
            isOn: true
        },
        {
            title: "Entrada leste",
            selectedColor: "#219653",
            isOn: true
        }
    ]
</script>

<div class="fml-controls">
    {#each controls as control}
        <FmlControl 
            bind:title={control.title}
            bind:selectedColor={control.selectedColor}
            bind:isOn={control.isOn}>
        </FmlControl>
    {/each}
</div>

<style>
	 .fml-controls {
        height: 100%;
        display: grid;
        grid-gap: 1.5rem;
        grid-template-columns: repeat( auto-fit, minmax(19rem, 1fr) );
        grid-auto-rows: min-content;
        width: 100%;
        margin: 0 auto;
        align-items: start;
    }
</style>