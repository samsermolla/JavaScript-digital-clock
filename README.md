# DigitalClock


# Build your own digital clock with JavaScript
## What we want to have
- Display current date
- Display current time
- Increment the time on it's own

## Technology we use
- ***Javascript***

# The Javascript
The entire code for the working of the clock is written within the `tick()` function. Inside this function, an object of the `Date()` is created which allows you to call year, date, hour, minute, second.

```
var date = new Date();
```
In our code, this object is used for getting the current hours, minutes and seconds which are stored in different variables.
```
var h = date.getHours(); 
var m = date.getMinutes();
var s = date.getSeconds();
```
The obtained hours, minutes and seconds will be displayed in single digit if less than 10. For example, the current hour will be displayed as 7 instead of 07. To always display the elements of time in two-digit format, a 0 is appended before them whenever they are less than 10
```
 h = (h < 10) ? "0" + h : h;
 m = (m < 10) ? "0" + m : m;
 s = (s < 10) ? "0" + s : s;
```
Now once our time is ready, let's display it in the div which we made before. This is done by obtaining the div using the document.getElementById method and give our time as the content of the div using the innerHTML property.
```
document.getElementById("MyClockDisplay").innerText = time;
document.getElementById("MyClockDisplay").textContent = time;
```
# Base design
Make the basic html structure
```
<!DOCTYPE html>
<html lang="en">

<head>
    <title>Digital Clock</title>

</head>

<body>
    <h1>Digital Clock</h1>
    <div id="MyClockDisplay" class="clock" onload="showTime()"></div>

</body>

</html>
```
Attach CSS
```
<link rel="stylesheet" href="css/digitalclock.css">
```
Attach Javascript file
```
<script src="js/digitalclock.js"></script>
```
# The Styling
Will add a nice font it will center the hero div and make the background fit nicely
```
body {
    background: black;
}

.clock {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translateX(-50%) translateY(-50%);
    color: #17D4FE;
    font-size: 60px;
    font-family: Orbitron;
    letter-spacing: 7px;
   


}
```




