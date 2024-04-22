<script lang="ts">

    export let d = 6;
    let rolled;
    let rolledText = "You haven't rolled yet.";
    let rollHistory = [];
    let roll = () => {
        rolled = Math.floor(Math.random() * d + 1);
        rollHistory[rollHistory.length] = rolled;

        rolledText = "You rolled " + rolled
    }


</script>

<style>
    div {
        background-color: bisque;
        min-width: fit-content;
        max-width: 100%;
        border: 2px black solid;

    }
    p {
        font-size: 2em;
    }
</style>

<div>
    <p> This is dice with {d} eyes. </p>
    <p>{rolledText}</p>

    <button on:click={roll}>Throw d{d}</button>
</div>