<script>
    export let property;
    export let handleBuy;
    export let balance;
</script>

<div class="property">
    <h3>{property.name}</h3>
    <p>Type: {property.type}</p>
    <p>Color: {property.color}</p>
    <p>Cost: ${property.cost}</p>
    <button on:click={() => {handleBuy(property)}}>Kup</button>
</div>

<style>
    .property {
        border: 1px solid #ccc;
        padding: 10px;
        margin: 10px;
        width: 200px;
    }
</style>
