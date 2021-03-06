# CPBSB3-CTF Writeup

### Challenge: 
>Kishor Balan tipped us off that the following code may need inspection: https://2019shell1.picoctf.com/problem/61676/ (link) or http://2019shell1.picoctf.com:61676

### Hints:
>How do you inspect web code on a browser?

>There's 3 parts

- **Passos:**
	Get the source code of the page with `ctrl+U`. There you will see this:

	```<!doctype html>
	<html>
	  <head>
	    <title>My First Website :)</title>
	    <link href="https://fonts.googleapis.com/css?family=Open+Sans|Roboto" rel="stylesheet">
	    <link rel="stylesheet" type="text/css" href="mycss.css">
	    <script type="application/javascript" src="myjs.js"></script>
	  </head>

	  <body>
	    <div class="container">
	      <header>
		<h1>Inspect Me</h1>
	      </header>

	      <button class="tablink" onclick="openTab('tabintro', this, '#222')" id="defaultOpen">What</button>
	      <button class="tablink" onclick="openTab('tababout', this, '#222')">How</button>
	      
	      <div id="tabintro" class="tabcontent">
		<h3>What</h3>
		<p>I made a website</p>
	      </div>

	      <div id="tababout" class="tabcontent">
		<h3>How</h3>
		<p>I used these to make this site: <br/>
		  HTML <br/>
		  CSS <br/>
		  JS (JavaScript)
		</p>
		<!-- Html is neat. Anyways have 1/3 of the flag: picoCTF{tru3_d3 -->
	      </div>
	      
	    </div>
	    
	  </body>
	</html>
	```

	At this point we already have the first part of the flag `picoCTF{tru3_d3`. Now let's get a look on the js file script `<script type="application/javascript" src="myjs.js"></script>`.

	```
	function openTab(tabName,elmnt,color) {
		    var i, tabcontent, tablinks;
		    tabcontent = document.getElementsByClassName("tabcontent");
		    for (i = 0; i < tabcontent.length; i++) {
			tabcontent[i].style.display = "none";
		    }
		    tablinks = document.getElementsByClassName("tablink");
		    for (i = 0; i < tablinks.length; i++) {
			tablinks[i].style.backgroundColor = "";
		    }
		    document.getElementById(tabName).style.display = "block";
		    if(elmnt.style != null) {
			elmnt.style.backgroundColor = color;
		    }
		}

		window.onload = function() {
		    openTab('tabintro', this, '#222');
		}

		/* Javascript sure is neat. Anyways part 3/3 of the flag: _lucky?1638dbe7} */
	```
	Now we have the last part of the flag, now we need get the second one `_lucky?1638dbe7}`. Just go to the css file and see the source code to, you will get this `/* You need CSS to make pretty pages. Here's part 2/3 of the flag: t3ct1ve_0r_ju5t */`

#### Flag: **picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?1638dbe7}**
