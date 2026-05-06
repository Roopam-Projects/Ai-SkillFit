# Ai-SkillFit
Ai Bharat Project - An innovative solution using AI to improve daily life experiences.
<!DOCTYPE html>
<html>
<head>
    <title>AI SkillFit</title>
    <style>
        body {
            font-family: Arial;
            text-align: center;
            background: #f4f4f4;
        }
        .container {
            width: 50%;
            margin: auto;
            background: white;
            padding: 20px;
            border-radius: 10px;
            margin-top: 50px;
            box-shadow: 0px 0px 10px gray;
        }
        input, textarea {
            width: 80%;
            padding: 10px;
            margin: 10px;
        }
        button {
            padding: 10px 20px;
            background: blue;
            color: white;
            border: none;
            cursor: pointer;
            border-radius: 5px;
        }
        button:hover {
            background: darkblue;
        }
        #interview, #resultBox {
            display: none;
        }
    </style>
</head>

<body>

<div class="container">
    <h2>AI SkillFit Interview System</h2>

    <!-- Candidate Name -->
    <input type="text" id="name" placeholder="Enter your name">

    <br>
    <button onclick="startInterview()">Start Interview</button>

    <!-- Interview Section -->
    <div id="interview">
        <h3>Question:</h3>
        <p>Tell me about yourself</p>

        <textarea id="answer" rows="5" placeholder="Type your answer here..."></textarea>

        <br>
        <button onclick="submitAnswer()">Submit Answer</button>
    </div>

    <!-- Result Section -->
    <div id="resultBox">
        <h3>Result</h3>
        <p id="result"></p>
        <p id="score"></p>
    </div>

</div>

<script>

function startInterview() {
    let name = document.getElementById("name").value;

    if(name == ""){
        alert("Please enter your name first!");
        return;
    }

    document.getElementById("interview").style.display = "block";
}

function submitAnswer() {
    let answer = document.getElementById("answer").value;
    let score = answer.length;

    let result = "";

    if(score > 80){
        result = "Job Ready ✅";
    } 
    else if(score > 40){
        result = "Needs Training ";
    } 
    else {
        result = "Manual Review ";
    }

    document.getElementById("result").innerHTML = "Status: " + result;
    document.getElementById("score").innerHTML = "Score: " + score;

    document.getElementById("resultBox").style.display = "block";
}

</script>

</body>
</html>
