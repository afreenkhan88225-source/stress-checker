<!DOCTYPE html>
<html>
<head>
<title>Stress Checker</title>

<style>
body {
    font-family: Arial;
    background: #eef5ff;
    text-align: center;
    transition: 0.3s;
}

.box {
    background: white;
    padding: 20px;
    width: 320px;
    margin: 40px auto;
    border-radius: 10px;
    box-shadow: 0 0 10px gray;
}

select, input, button {
    margin: 8px;
    padding: 8px;
    width: 90%;
}

/* DARK MODE */
.dark {
    background: #222;
    color: white;
}

.dark .box {
    background: #333;
    color: white;
}

.dark select,
.dark input,
.dark button {
    background: #444;
    color: white;
    border: 1px solid white;
}

.dark h2 {
    color: #00ffff;
}

</style>
</head>

<body>

<h2>🧠 Stress Checker</h2>

<button onclick="toggleDark()">🌙 Dark Mode</button>

<div class="box">

<input type="text" id="name" placeholder="Enter your name">

<p>Sleep</p>
<select id="sleep">
<option value="1">Good</option>
<option value="2">Average</option>
<option value="3">Poor</option>
</select>

<p>Mood</p>
<select id="mood">
<option value="1">Happy</option>
<option value="2">Normal</option>
<option value="3">Sad</option>
</select>

<p>Work Pressure</p>
<select id="work">
<option value="1">Low</option>
<option value="2">Medium</option>
<option value="3">High</option>
</select>

<p>Energy</p>
<select id="energy">
<option value="1">High</option>
<option value="2">Medium</option>
<option value="3">Low</option>
</select>

<button onclick="checkStress()">Check Stress</button>

<h3 id="result"></h3>

</div>

<script>
function checkStress() {
    let name = document.getElementById("name").value || "User";

    let score =
    +sleep.value + +mood.value + +work.value + +energy.value;

    let result = "";
    let color = "";

    if(score <=5){
        result="Low Stress 😊";
        color="green";
    } else if(score<=8){
        result="Medium Stress 😐";
        color="orange";
    } else {
        result="High Stress 😟";
        color="red";
    }

    document.getElementById("result").innerHTML =
    name + ": <b style='color:"+color+"'>" + result + "</b>";
}

function toggleDark(){
    document.body.classList.toggle("dark");
}
</script>

</body>
</html>
