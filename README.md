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
Once this is done, we extract the hours, minutes, and seconds from the variable (date) using the `getHours()`, `getMinutes()` and `getSeconds()` methods.

These methods return the respective values when a date is passed, we store them in different variables.

And lastly, we use a variable called` "session"` to store the` AM `or` PM` tag.
```
let hh = date.getHours();
let mm = date.getMinutes();
let ss = date.getSeconds();
let session = "AM";
```
**Note :** Here date in `date.getHours()`, etc, is the variable we used to store the current date earlier.

The date.getHours method returns values between 0-23, and given we are programming a 12 hours clock we use the following if statement to reset 12 to 0.
```
if(hh == 0){

      hh = 12;

  } 
```
And, we use another if to subtract hours greater than 12 and to assign the value of the session variable to “PM”.
```
if(hh > 12){

    hh = hh - 12;

    session = "PM";

  } 
```
To understand the next bit of code, you need to be familiar with two concepts.

Firstly, the `getHours()`,` getMinutes()` and` getSeconds() `methods return values between `0 to 23, 59, 59` respectively. The key point here is that single digit values are returned as # (eg: 7), however, in our clock, these values need to be displayed as ## (eg: 07).

And to achieve this we use ternary operators. This operator returns a value if the condition is true and another value if it is false. I’ve added the syntax below.
```
(condition ? if true : if false); 
```
Using this operator, we solve the above problem by adding a 0 before the digit that is less than 10.
```
 h = (h < 10) ? "0" + h : h;
 m = (m < 10) ? "0" + m : m;
 s = (s < 10) ? "0" + s : s;
```
Next, we create a variable time to store the time in the desired format.
```
let time = hh + ":" + mm + ":" + ss + " " + session; 
```
To display the time we use the following code.
```
document.getElementById("clock").innerText = time 
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




