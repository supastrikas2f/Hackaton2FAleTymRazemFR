<script context="module">
    let labelCounter = 0;
</script>
<script>
	export let name;
    let eltWins = 'input_' + labelCounter++;    
    let eltScore = 'input_' + labelCounter++;
    let eltMoney = 'input_' + labelCounter++;

    let wins = 0;
    let showWins = false;

    function addWins(){
        wins++;
    }
    function substractWins(){
        if(wins > 0) wins--;
    }
    function resetWins(){
        wins = 0;
    }
    
    let score = 0;
    let showScore = false;
    let scoreCustomSubstract = 0;
    let scoreCustomAdd = 0;
    
    function addScore(number){
        score += number;
    }
    function substractScore(number){
        let temp = score - number;
        score = temp < 0 ? 0 : temp;
    }
    function resetScore(){
        score = 0;
    }

    let money = 0;
    let showMoney = false;
    let moneyToAdd;
    let moneyToSubstract;
    
    
    function addMoney(){
        if(typeof(moneyToAdd) === "number") {money += moneyToAdd;}
    }
    function substractMoney(){
        let temp = money - moneyToSubstract;
        if(typeof(moneyToSubstract) === "number") money = temp < 0 ? 0 : temp;
    }
    function resetMoney(){
        money = 0;
    }
   
</script>

<style>
	input::-webkit-outer-spin-button,
    input::-webkit-inner-spin-button {
        -webkit-appearance: none;
        margin: 0;
    }
    input[type=number] {
        -moz-appearance: textfield;
    }
    
    #PlayerBox{     
        width: 350px;
        height: 400px; 
        text-align: center;      
    }
    
    ul{
        text-align: left;
        list-style: none;
    }

    #ScoreTab input{
        width: 50px;
    }

    #MoneyTab input{
        width: 100px;
    }
</style>

<div id="PlayerBox">
    <h2>{name}</h2>
    
    <ul>
        <li><input type="checkbox" id="{eltWins}" bind:checked = {showWins}><label for="{eltWins}">Wins</label></li>
        <li><input type="checkbox" id="{eltScore}" bind:checked = {showScore}><label for="{eltScore}">Score</label></li>
        <li><input type="checkbox" id="{eltMoney}" bind:checked = {showMoney}><label for="{eltMoney}">Money</label></li>
    </ul>
    
    <div id="InfoTab">       
        {#if showWins === true}
            <div id="WinsTab">  
                <h3>Wins: {wins} <button on:click={addWins}>+</button> <button on:click={substractWins}>-</button> <button on:click={resetWins}>Reset</button></h3>
            </div>   
        {/if}        
        {#if showScore === true}
            <div id="ScoreTab">  
                <h3>Score: {score} <button on:click={resetScore}>Reset</button></h3>
                <div id="ScoreAddTab">
                    <button on:click={() => addScore(1000)}>+1000</button>
                    <button on:click={() => addScore(100)}>+100</button>
                    <button on:click={() => addScore(10)}>+10</button>
                    <button on:click={() => addScore(1)}>+1</button>
                    <input type="number" id="customScoreAdding" bind:value={scoreCustomAdd}><button on:click={() => addScore(scoreCustomAdd)}>Add</button>
                </div>
                <div id="ScoreSubstractTab">
                    <button on:click={() => substractScore(1000)}>-1000</button>
                    <button on:click={() => substractScore(100)}>-100</button>
                    <button on:click={() => substractScore(10)}>-10</button>
                    <button on:click={() => substractScore(1)}>-1</button>
                    <input type="number" id="customScoreSubtraction" bind:value={scoreCustomSubstract}><button on:click={() => substractScore(scoreCustomSubstract)}>Substract</button>
                </div>
            </div>
        {/if}      
        {#if showMoney === true}
            <div id="MoneyTab">   
                <h3>Money: {money} <button on:click={resetMoney}>Reset</button></h3>
                <input type="number" id="addMoney" bind:value={moneyToAdd}><button on:click={addMoney}>Add</button>
                <input type="number" id="substractMoney" bind:value={moneyToSubstract}><button on:click={substractMoney}>Substract</button>
            </div>
        {/if}
        
    </div>
</div>