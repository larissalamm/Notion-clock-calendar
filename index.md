<!-- original : https://codepen.io/SeanNorton/pen/LWBXQL -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calendar</title>

    <style>
body{
    background-color: #fff;
    line-height: 1.8;

}

h1 {
    margin-top: 0;
}

    </style>
</head>
<body>
    <link href="https://fonts.googleapis.com/css?family=Roboto" rel="stylesheet">

<div class="full-table">
  <div class="table-cell">
    
      <div class="clock">
        <div class="time" id="hour"></div>
        <div class="colon">:</div>
        <div class="time" id="min"></div>
        <div class="colon">:</div>
        <div class="time" id="sec"></div>
        <div class="date" id="date"></div>
        <div class="title" id="title"></div>
       <div class="greet" id="greet"></div>
      </div>
    </div>
    
  </div>
</div>

/*CSS START*/

.full-table {
    display: table;
    height: 100%;
    width: 100%;
}

.table-cell {
    display: table-cell;
    vertical-align: middle;
    text-align: center;
}

.card:hover {
    margin-top: 0px;
    box-shadow: none;
}

.clock {
    display: inline-block;
    font-family: 'Roboto', normal;
    font-weight: bold;
    font-size: 1.2em;
    line-height: 1.5em;
    /* padding-left: 20px; */
}

.time {
    display: inline-block;
    min-width: 25px;
    font-size: 1.5em;
}

.colon {
    font-size: 1.2em;
    display: inline-block;
}

.date {
    display: block;
    min-width: 162px;
    /* padding-right: 30px; */
    /* border-right: 2px solid #295C7B; */
    font-family: 'Roboto', sans-serif;
    font-weight: 400;
    font-size: 1em;
    line-height: 1.9em;
}
.greet{
    
    min-width: 162px;
    /* padding-right: 30px; */
    font-family: 'Roboto', sans-serif;
    font-size: 0.9em;
    font-style: bold;
    font-weight: 500;
    line-height: 1.3em;
    color: #424242;
}
.title{
    font-family: 'Roboto', sans-serif;
    font-weight: 400;
    font-size: 0.95em;
    font-style: regular;
    text-decoration: underline #636363;
   
}

<script>

    function date() {
var today = new Date();
const options = { weekday: 'long', year: 'numeric', month: '2-digit', day: '2-digit' };
document.getElementById('date').innerHTML =
today.toLocaleDateString('de-DE', options);
}

function clock() {
var today = new Date();
var hour = zeros(today.getHours());
var minutes = zeros(today.getMinutes());
var seconds = zeros(today.getSeconds());

{}
hrs = today.getHours();
if (hrs < 7)
        greet = 'Schon wach!?';
    else if (hrs >= 7 && hrs < 12)
        greet = 'Guten Morgen!';
    else if (hrs >= 12 && hrs < 16)
        greet = 'Schon Alles eingetragen?';
    else if (hrs >= 16 && hrs < 19)
        greet = 'Schon Klavier gespielt?';
    else if (hrs >=19 && hrs < 21)
        greet = 'Alles erledigt?'
    else if (hrs >= 21 && hrs <= 24)
        greet = 'Gute Nacht!';
title = 'Current tasks:'
// console.log(today.toLocaleTimeString());
document.getElementById('title').innerHTML = title;
document.getElementById('greet').innerHTML = greet;
document.getElementById('hour').innerHTML = hour;
document.getElementById('min').innerHTML = minutes;
document.getElementById('sec').innerHTML = seconds;
}

// adds zero infront of single digit number
function zeros(num) {
if (num < 10) {
    num = '0' + num
};
return num;
}

function dateTime() {
date();
clock();
setTimeout(dateTime, 500);
}

dateTime()
// END
</script>

</html>
