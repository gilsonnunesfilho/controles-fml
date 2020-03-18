<script>
    import ColorBlocks from '../fml-controls/color-blocks.svelte'

    import { slide } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';

    export let selectedColor = ""
    export let isExpanded = false

    function togglePanel() {
        isExpanded = !isExpanded
    }
</script>

<button on:click={togglePanel} class="collapse-trigger">
    <span>
        <slot></slot>
    </span>
    <i class="material-icons">keyboard_arrow_down</i>
</button>
{#if isExpanded}
<div class="collapse-panel" transition:slide="{{delay: 0, duration: 300, easing: quintOut }}" >
    <ColorBlocks bind:selectedColor />
</div>
{/if}

<style>
    .collapse-trigger {
        width: 100%;
        font-size: 1rem;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 1rem;
        box-sizing: border-box;
        margin: 0;
        background-color: transparent;
        border: none;
        -webkit-tap-highlight-color: transparent;
    }
</style>