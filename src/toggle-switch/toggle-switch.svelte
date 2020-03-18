<script>
    export let isOn = true
    export let selectedColor = ""
</script>

<label style="--selected-color: {selectedColor}">
    <input type="checkbox" bind:checked={isOn}>
    <span class="slider"></span>
</label>

<style>
    label {
        --selected-color: rebeccapurple;
        position: relative;
        display: inline-block;
        width: 3.125rem;
        height: 2.5rem;
        padding: .5rem;
        -webkit-tap-highlight-color: transparent;
    }

    label input {
        opacity: 0;
        width: 0;
        height: 0;
    }

    span {
        position: absolute;
        cursor: pointer;
        display: flex;
        align-items: center;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        transition: 200ms;
        border-radius: 9999px;
        color: var(--selected-color);
    }

    span::before {
        content: "";
        position: absolute;
        left: .5rem;
        width: 2.125rem;
        height: .875rem;
        border-radius: 9999px;
        background-color: #000;
        box-sizing: border-box;
        border: 1px solid rgba(0,0,0,.456);
        opacity: .38;
    }

    span::after {
        content: "";
        position: absolute;
        left: .5rem;
        height: 1.25rem;
        width: 1.25rem;
        border-radius: 9999px;
        background-color: #fff;
        opacity: 1;
        transition: background-color, opacity, transform;
        transition-duration: 90ms;
        transition-timing-function: ease-out;
        will-change: transform, background-color, opacity;
        box-shadow: 0px 1px 3px rgba(0, 0, 0, 0.2), 0px 2px 1px rgba(0, 0, 0, 0.12), 0px 1px 1px rgba(0, 0, 0, 0.14);
    }

    input:checked + span::before {
        background-color: currentColor;
    }

    input:focus + span::before {
        opacity: .6;
    }

    input:checked + span::after {
        transform: translateX(.875rem);
        background-color: currentColor;
        opacity: 1;
    }

</style>