<script>
import propertiesData from '../properties.json';
  import TransferForm from './TransferForm.svelte';
  import Property from './Property.svelte';

  
  let balance = 1500;
  let properties = propertiesData.properties;
  let buyedProperties = [];
  let players = [
    { name: 'Gracz 1', balance: 1500 },
    { name: 'Gracz 2', balance: 1500 }
  ];
  function handleBuy(property) {
    if(balance >= property.cost) {
      buyedProperties.push(property);
      properties[properties.indexOf(property)] = null;
      balance -= property.cost;
    }
    }

</script>

<h1>Bankier Monopoly</h1>
<h2>Saldo: {balance}</h2>

<TransferForm {players} />

<div class="properties-container">
    <h1>Zakupione nieruchomości</h1>
    {#each buyedProperties as property}
      <Property property = {property} handleBuy = {handleBuy} {balance} />
    {/each}
    <h1>Nieruchomości do zakupienia</h1>
    {#each properties as property}
        {#if property != null}
      <Property property = {property} handleBuy = {handleBuy} {balance} />
        {/if}
    {/each}
  </div>
