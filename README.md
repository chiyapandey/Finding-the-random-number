//Create a javascript program to take a random number between 1 to 10  and ask the user to guess it. Provide hints (higher/lower) until they guess it correctly.
<!DOCTYPE html>
<html>
<head>
    <title>Number Guessing Game</title>
</head>
<body>
    <h1>Number Guessing Game</h1>
    <p>Guess a number between 1 and 10:</p>
    <input id="input" type="number" min="1" max="10">
    <button onclick="checkGuess()">Submit</button>
    <p id="result"></p>

    <script>
        let randomGeneratedNumber = Math.floor(Math.random() * 10) + 1;
        let attempts = 0;

        function checkGuess() {
            let userInputtedValue = parseInt(document.getElementById("input1").value);

            if (isNaN(userInputtedValue) || userInputtedValue < 1 || userInputtedValue > 10) {
                document.getElementById("result").innerHTML = "Please enter a valid number between 1 and 10.";
                return;
            }

            attempts++;

            if (userInputtedValue === randomGeneratedNumber) {
                document.getElementById("result").innerHTML = `Congratulations! You guessed the number ${randomGeneratedNumber} in ${attempts} attempts.`;
            } else if (userInputtedValue < randomGeneratedNumber) {
                document.getElementById("result").innerHTML = "Your guess is too low. Try again.";
            } else {
                document.getElementById("result").innerHTML = "Your guess is too high. Try again.";
            }
        }
    </script>
</body>
</html>
