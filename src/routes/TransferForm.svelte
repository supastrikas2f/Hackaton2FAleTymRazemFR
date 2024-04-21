<script>
  import { createEventDispatcher } from 'svelte';

  export let players;

  const dispatch = createEventDispatcher();
  let receiver;
  let amount;

  const handleTransfer = () => {
    dispatch('transfer', {receiver, amount });
    receiver = '';
    amount = '';
  };
</script>

<div>
  <h2>Przelew</h2>

  <select bind:value={receiver}>
    {#each players as player}
      <option value={player.name}>{player.name}</option>
    {/each}
  </select>

  <input type="number" bind:value={amount} placeholder="Kwota" />

  <button on:click={handleTransfer}>Wykonaj przelew</button>
</div>
