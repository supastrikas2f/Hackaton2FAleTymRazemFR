<script>
    import Dice from "../../components/Dice.svelte"
    $: dice = [];
    let number;
    function addDice(number)
    {
        if(number > 0)
        {
        dice.push(number)
        dice = dice;
        }else{alert("Podaj liczbę oczek")}

    }
</script>

<style>
    #flexBox{
        display: flex;
        align-items: center;
        justify-content: center;
    }
   
    #grid{
        display: inline-grid;
        grid-template-columns: auto auto auto auto;      
        margin: auto; 
        border: 1px solid black;
        min-width: 80%;
        min-height: 30em;
    }
    
    #addDice{
        display: flex;
        align-items: center;
        width: 350px;
        height: 200px; 
        margin: 10px;
    }

    #addDice input{
        width: 150px;
        margin: 20px;
    }

    #diceBox{
        margin: 20px;
    }

    #deleteDice{
        left: 33%;
        margin: 15px;
    }

    
</style>

<p>Podaj liczbę oczek</p>
<div id="addDice" class="boxesMargin">
    <input type="number" bind:value = {number}> 
    <button on:click={() => addDice(number)}>Add Dice</button>  
</div>
<div id="flexBox">
    <div id="grid">    
        {#each dice as number}   
            {#if number !== null}    
                <div id="diceBox">
                    <Dice d = {number} class="boxesMargin"></Dice> 
                           
                </div>
            {/if} 
        {/each}  
    </div>
</div>
