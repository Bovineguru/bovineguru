## Hi there 👋

I'm currently working on a cypher program that is difficult to solve.


<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Decrypt the Love Letter</title>
<script>
function decrypt() {
    var userInput = document.getElementById("decryptedText").value;
    var shift = 3; // Change this based on your encryption
    var decryptedMessage = "";

    for (var i = 0; i < userInput.length; i++) {
        var c = userInput.charCodeAt(i);
        if (c >= 65 && c <= 90) {
            decryptedMessage += String.fromCharCode((c - 65 - shift + 26) % 26 + 65); // Uppercase
        } else if (c >= 97 && c <= 122) {
            decryptedMessage += String.fromCharCode((c - 97 - shift + 26) % 26 + 97); // Lowercase
        } else {
            decryptedMessage += String.fromCharCode(c);
        }
    }

    if (decryptedMessage === "LOVE") { // Change "LOVE" to your original message
        alert("Congratulations! You've decrypted the message: " + decryptedMessage);
    } else {
        alert("Try again!");
    }
}
</script>
</head>
<body>
<h1>Decrypt the Love Letter</h1>
<p>Type your guess here:</p>
<input type="text" id="decryptedText">
<button onclick="decrypt()">Decrypt</button>
</body>
</html>
