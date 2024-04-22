<html lang="">
    <head>
        <meta chaset="utf-8">
        <title>Hakaton - Supastrikas2F</title>
    </head>
    <body>
        <div id="functions">
            <h1>Dostępne Funkcje</h1>
            <div id="centerLinks">
                <div id="links">
                    <a href="/playersBoxes">Dodawanie Graczy</a>
                    <a href="/rudy">System Banku Monopoly</a>
                    <a href="/Dice">Rzut Koścmi</a>
                </div>
            </div>
        </div>
    </body>
</html>
<style>
    *{
        font-family: Arial, Helvetica, sans-serif;
    }

    #centerLinks{
        margin-top: 5em;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    #functions{
        position: relative;
        margin-top: 5.5em;
        left: 18%;
        border: 10px solid #0085be;
        border-radius: 30px ;
        height: 700px;
        width: 600px;
        background-color: #92deff;
    }

    #links{
        display: grid;
        grid-template-columns: auto;       
    }

    h1{
        background-color: #88d6f5;
        text-align: center;
        padding: 0.5em;
        margin-top: 2em;
    }
    
    a{
        font-weight: bold;
        font-size: 30px;
        text-align: center;
        padding: 1.2em 1.5em;
        text-decoration: none;       
        color: black;
        border: 5px solid #aee8ff;
        border-radius: 10px;
        width: 400px;
        margin: 0.7em 0em;
        background-color: #aee8ff;
    }

    a:hover{
        color: rgb(0, 46, 107);
        border-color: #00529e;
        background-color: #bfebfd;
    }

</style>