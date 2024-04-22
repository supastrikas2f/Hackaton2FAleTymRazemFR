<script>
	import Player from "../../components/Player.svelte";

    $: players = [];  
    let name;
    
    function addPlayer(){     
        if(typeof(name) === "string"){
            players.push(name);
            players = players;
        }else alert("Podaj nazwę gracza");    
    }

    function deletePlayer(name){
        players[players.indexOf(name)] = null;
    }
</script>

<style>
    *{
        font-family: Arial, Helvetica, sans-serif;
    }
    
    #flexBox{
        display: flex;
        align-items: center;
        justify-content: center;
    }
   
    #grid{
        display: inline-grid;
        grid-template-columns: auto auto auto auto;      
        margin: auto; 
    }
    
    #addPlayerBox{
        display: flex;
        align-items: center;
        width: 350px;
        height: 500px; 
        margin: 10px;
    }

    #addPlayerBox input{
        border: none;
        border-radius: 10px;
        background-color: rgb(202, 240, 255);
        width: 220px;
        height: 50px;
        margin: 20px;
        text-align: center;
        font-weight: bold;
        font-size: 20px;
    }

    #buttonAddPlayer{
        font-size: 20px;
        padding: 0.2em 1.3em;
    }

    #playerBox{
        border: 5px solid black;
        border-radius: 40px;
        margin: 20px;
        background-color: #bfebfd;
    }

    #deletePlayer{
        position:relative;
        left: 33%;
        margin: 15px;
    }
    
</style>

<div id="flexBox">
    <div id="grid">    
        {#each players as name}   
            {#if name !== null}    
                <div id="playerBox">
                    <Player name = {name} class="boxesMargin"></Player> 
                    <button id="deletePlayer" on:click={() => deletePlayer(name)}>Delete Player</button>             
                </div>
            {/if} 
        {/each}   

        <div id="addPlayerBox" class="boxesMargin">
            <input type="text" bind:value = {name}> 
            <button id="buttonAddPlayer" on:click={addPlayer}>Add Player</button>
        </div>
    </div>
</div>