<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>My Work App</title>
<style>
body { font-family: Arial; padding: 20px; text-align: center; }
button { font-size: 20px; padding: 15px; margin: 10px; width: 90%; }
</style>
</head>
<body>

<h2>My Work App</h2>

<button onclick="startWork()">I Came</button>
<button onclick="endWork()">I Left</button>

<p id="result"></p>

<script>
function startWork() {
  localStorage.setItem("start", new Date());
  alert("Work started");
}

function endWork() {
  let start = new Date(localStorage.getItem("start"));
  let end = new Date();
  let hours = (end - start) / 3600000;
  let rate = 15; // hourly salary
  let pay = hours * rate;
  document.getElementById("result").innerHTML =
    "Hours: " + hours.toFixed(2) + "<br>Salary: $" + pay.toFixed(2);
}
</script>

</body>
</html>
