<!DOCTYPE html>
<html lang="en">
    <head>
      <meta charset="UTF-8">
      <title>Rock Paper Scissors</title>
      <link rel="stylesheet" href="style.css">
    </head>
<body>
<h1>Rock Paper Scissors</h1>
    <div id="results">
    </div>    
    <div class="buttons"> 
        <button id = "rock"> <img class="images"; src="https://www.kindpng.com/picc/b/266/2667213.png"; alt="Rock" > </button>
        <button id = "paper"> <img class="images"; src="https://www.kindpng.com/picc/b/266/2667881.png"; alt="Paper"> </button>
        <button id = "scissors"> <img class="images"; src="https://www.clipartkey.com/mpngs/m/109-1094404_rock-paper-scissors-png.png"; alt="Scissors"> </button>
    </div> 
<script>
    let counterPlayer = 0;
    let counterComp = 0;
    let message;
    let options = ["rock", "paper", "scissors"];
    function computerPlay() {
        let currentPlay = Math.floor(Math.random()*3);
        let computerChoice = options[currentPlay];
        return computerChoice;
    }
    function playRound(playerSelection, computerSelection) {
        playerSelection = playerSelection.toLowerCase();
        if (playerSelection == computerSelection) {
            return ("It's a tie")
        } else if (playerSelection == "rock"){
            if  (computerSelection == "scissors") {
                counterPlayer++;
                return ("rock beats scissors, player wins!");
            } else {
                counterComp++;
                return ("paper beats rock, computer wins!");
            }
        } else if (playerSelection == "paper") {
            if  (computerSelection == "rock"){
                counterPlayer++;
                return ("paper beats rock, player wins!");
            } else {
                counterComp++;
                return ("scissors beat paper, computer wins!");
            }
        } else {
            if (computerSelection == "paper") {
                counterPlayer++;
                return ("scissors beat paper, player wins!");
            } else {
                counterComp++;
                return ("rock beats paper, computer wins!");
            }
        }
    }

const rock = document.querySelector('#rock');
const paper = document.querySelector('#paper');
const scissors = document.querySelector('#scissors');
const results = document.querySelector('#results');

const indResult = document.createElement('p');

rock.addEventListener("click", function(e) {
    if(counterPlayer < 4 && counterComp < 4) {
    result = playRound("rock", computerPlay());
    message = result + " You: " + counterPlayer + " Computer: " + counterComp;
    indResult.textContent = message;
    results.appendChild(indResult);
    return message;
    } else if (counterPlayer == 4 || counterComp == 4) {
       result = playRound("rock", computerPlay());
        if (counterPlayer == 5) {
            let message = "You win by 5 to " + counterComp;
            counterComp = 0;
            counterPlayer = 0; 
            indResult.textContent = message;
            results.appendChild(indResult); 
            return message; 
        } else if (counterComp == 5) {
            let message = "Computers win by 5 to " + counterPlayer;
            counterComp = 0;
            counterPlayer = 0;  
            indResult.textContent = message;
            results.appendChild(indResult);
            return message;
        } else {
            let message = result + " You: " + counterPlayer + " Computer: " + counterComp;  
            indResult.textContent = message;
            results.appendChild(indResult);
            return message;
        }
    }

});    

paper.addEventListener("click", function(e) {
    if(counterPlayer < 4 && counterComp < 4) {
    result = playRound("paper", computerPlay());
    message = result + " You: " + counterPlayer + " Computer: " + counterComp;
    indResult.textContent = message;
    results.appendChild(indResult);
    return message;
    } else if (counterPlayer == 4 || counterComp == 4) {
       result = playRound("paper", computerPlay());
        if (counterPlayer == 5) {
            let message = "You win by 5 to " + counterComp;
            counterComp = 0;
            counterPlayer = 0; 
            indResult.textContent = message;
            results.appendChild(indResult); 
            return message; 
        } else if (counterComp == 5) {
            let message = "Computers win by 5 to " + counterPlayer;
            counterComp = 0;
            counterPlayer = 0;  
            indResult.textContent = message;
            results.appendChild(indResult);
            return message;
        } else {
            let message = result + " You: " + counterPlayer + " Computer: " + counterComp;  
            indResult.textContent = message;
            results.appendChild(indResult);
            return message;
        }
    }

});    

scissors.addEventListener("click", function(e) {
    if(counterPlayer < 4 && counterComp < 4) {
    result = playRound("scissors", computerPlay());
    message = result + " You: " + counterPlayer + " Computer: " + counterComp;
    indResult.textContent = message;
    results.appendChild(indResult);
    return message;
    } else if (counterPlayer == 4 || counterComp == 4) {
       result = playRound("scissors", computerPlay());
        if (counterPlayer == 5) {
            let message = "You win by 5 to " + counterComp;
            counterComp = 0;
            counterPlayer = 0; 
            indResult.textContent = message;
            results.appendChild(indResult); 
            return message; 
        } else if (counterComp == 5) {
            let message = "Computers win by 5 to " + counterPlayer;
            counterComp = 0;
            counterPlayer = 0;  
            indResult.textContent = message;
            results.appendChild(indResult);
            return message;
        } else {
            let message = result + " You: " + counterPlayer + " Computer: " + counterComp;  
            indResult.textContent = message;
            results.appendChild(indResult);
            return message;
        }
    }

});    
</script>
</body>    
</html>
