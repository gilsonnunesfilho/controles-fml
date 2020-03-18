<script>
    import CollapsablePanel from '../collapsable-panel/collapsable-panel.svelte'
    import ToggleSwitch from '../toggle-switch/toggle-switch.svelte'

    export let title = ""
    export let selectedColor = ""
    export let isOn = true
</script>

<div class="fml-control" class:disabled={!isOn}>
    <header>
        <h2>{title}</h2>
    </header>

    <CollapsablePanel bind:selectedColor>
        Selecionar cor
    </CollapsablePanel>

    <div class="selected-color" style="--selected-color: {selectedColor}"></div>

    <footer class="card-actions">
        <ToggleSwitch bind:isOn {selectedColor} />
        <button class="more-trigger">
            <i class="material-icons">more_vert</i>
        </button>
    </footer>
</div>

<style>
    .fml-control {
        background-color: white;
        border-radius: .25rem;
    }

    .fml-control.disabled {
        background-color: #ccc;
    }

    header {
        padding: 1.5rem 1rem 1rem;
    }

    h2 {
        font-size: 1.25rem;
        font-weight: 500;
        margin: 0;
    }

    .selected-color {
        height: 4.5rem;
        background-color: var(--selected-color, rgb(128,128,128));
        box-sizing: border-box;
        border: 1px solid rgba(0,0,0,.12);
        border-radius: .125rem;
        margin: 1rem;
    }

    .card-actions {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: .5rem;
        position: relative;
    }

    .card-actions::after {
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 1px;
        background-color: black;
        opacity: .12;
    }

    .more-trigger {
        width: 2.5rem;
        height: 2.5rem;
        border: none;
        background-color: transparent;
        margin: 0;
    }
</style>