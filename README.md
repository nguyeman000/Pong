<HEAD>
<SCRIPT LANGUAGE="JavaScript">
<!--  Begin
var crlf = "\r\n";
var x = 1;
var y = 1;
var dx = 1;
var dy = 1;
var s = "";
var u = 0;
var oops_flag = false;
var score = 0;
function move1() {
x += dx;
if (x > 31) {
x -= 2 * Math.abs(dx);
if (dx > 0) dx = -dx;
}
if (x <  0) {
x += 2 * Math.abs(dx);
if (dx < 0) dx = -dx;
}
y += dy;
if (y > 14) {
y -= 2 * Math.abs(dy);
if (dy > 0) dy = -dy;
if (Math.abs(x - 2*u - 1) > 2) {
oops_flag = true;
}
else {
score += 1;
   }
}
if (y <  0) { y += 2 * Math.abs(dy);
if (dy < 0) dy = -dy; }
}
function display1() {
var s1 = ""
var i,j;
if (oops_flag) return "Oops!! That one got by you!  Feel free to play again!";
for (j=0;j<15;j++) {
for (i=0;i<32;i++) {
if (j == y && i == x) s1 += "o";
else s1 += ".";
}
s1 += crlf;
}
var s2 = "";
for (i=0;i<16;i++) {
if (u == i) s2 += "==";
 else s2 += "..";
}
return (s1+s2);
}
var timerID = null;
var timerRunning = false;
var myform;
function stopclock (){
if(timerRunning) clearTimeout(timerID);
timerRunning = false;
}
function startclock (form) {
myform = form;
oops_flag = false;
if (navigator.userAgent.indexOf("Mac") > 2) crlf = "\n";
stopclock();
dotime();
}
function dotime() {
move1();
if (myform != null) {
myform.text3.value = display1();
myform.score.value = " " + score;
}
if (!oops_flag) timerID = setTimeout("dotime()",200);
timerRunning = true;
}
// End -->
</SCRIPT>
<BODY>
<center><h1>Pong</h1>
Press start to play.  Move the paddle by putting your cursor on the dashes.
<p>
<form name=form>
<textarea name=text3 rows=16 cols=34 wrap>[game field]</textarea><p>
<p>
<a href="" onMouseOver="u =0">\\\</a>
<a href="" onMouseOver="u =1">\\\</a>
<a href="" onMouseOver="u =2">\\\</a>
<a href="" onMouseOver="u =3">\\\</a>
<a href="" onMouseOver="u =4">\\\</a>
<a href="" onMouseOver="u =5">\\\</a>
<a href="" onMouseOver="u =6">\\\</a>
<a href="" onMouseOver="u =7">\\\</a>
<a href="" onMouseOver="u =8">\\\</a>
<a href="" onMouseOver="u =9">\\\</a>
<a href="" onMouseOver="u = 10">\\\</a>
<a href="" onMouseOver="u = 11">\\\</a>
<a href="" onMouseOver="u = 12">\\\</a>
<a href="" onMouseOver="u = 13">\\\</a>
<a href="" onMouseOver="u = 14">\\\</a>
<a href="" onMouseOver="u = 15">\\\</a>
<a href="" onMouseOver="u = 15">\\\</a><p>
<input type=button name=button1 value="Start" onCLick="startclock(this.form)">
Score: <input type=text name=score size=10 value=0>
</form>
</center>
</BODY>
</HEAD>
