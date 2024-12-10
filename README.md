<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<style>
    body{
        background-color: azure;
        font-family: Arial, Helvetica, sans-serif;
        margin:0;
        padding:0;
    }
    .container{
        max-width:400px;
        margin:100px  auto;
        text-align: center;
        background-color: #fff;
        padding:20px;
        border-radius: 10 px;
        box-shadow:0px 0px 10px black;
    }
    h1{
        font-size:28 px;
        color : #333;
    }
    input[type="text"]{
        width:95%;
        padding : 10px;
        margin-top : 20px;
        border: none;
        box-shadow: 0px 0px 5px rgb(83, 81, 81);
        font-size:16 px;
    }
    button{
        background-color: #007bff;
        color:#fff;
        border:none;
        padding: 10px 20px;
        border-radius: 5px;
        margin-top:20px;
        cursor:pointer;
        font-size:16px;
        transition: background-color 0.3s ease-in;
    }
    button:hover{
        background-color: #0056b3;
    }
    #result{
        margin-top:20px;
        font-size:18px;
        font-weight:bold;
    }
    @keyframes fadeIn {
        0%{
            opacity:0;
            transform:translateY(20px);
        }
        100%{
            opacity:1;
            transform:translateY(0);
        }
    }
    .fadeIn{
        animation:fadeIn 0.5s ease-in-out;
    }
</style>
<body>
    <div class="container">
        <h1>Palindrome Checker</h1>
        <input type="text" id="inputText" placeholder="Enter a Word">
        <button id="checkButton">Check</button>
        <div id="result">Result</div>
    </div>


    <script src="script.js"></script>
</body>
</html>

function isPalindrome(str) {
    const cleanStr = str.toLowerCase().replace(/[^a-z0-9]/g, '');
    console.log(cleanStr);

    const reversedStr = cleanStr.split('').reverse().join('');
    console.log(reversedStr);

    return cleanStr === reversedStr;
}

function palindromeChecker() {
   const inputText = document.getElementById("inputText");
   const result = document.getElementById("result");

   if (isPalindrome(inputText.value)) {
       result.textContent = `"${inputText.value}" is a Palindrome`;
   } else {
       result.textContent = `"${inputText.value}" is Not a Palindrome`;
   }

   result.classList.add('fadeIn');
   inputText.value = "";
}

document.getElementById('checkButton').addEventListener("click", palindromeChecker);
