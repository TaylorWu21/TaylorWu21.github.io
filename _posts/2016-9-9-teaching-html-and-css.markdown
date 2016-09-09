---
layout: post
title: "Teaching HTML and CSS"
date: 2016-9-9 15:18:00
category: HTML & CSS
---

This week I had the pleasure of teaching HTML and CSS to people who are interested in programming. Today I would love to share my knowledge of basic HTML and CSS. First you need a text editor I like to use [Sublime Text][sublimetext]. So what is HTML? HTML stands for Hyper Text Markup Language, it is a language that your web browser can interpret and display the output. CSS stands for Cascading Style Sheets, it is used to style your HTML.

[sublimetext]: https://www.sublimetext.com/3
___

After we have finished downloading a text editor lets get started by creating a new folder on the desktop. After you have created the folder click and drag it over your text editor icon to open it. Now we can create files within this foldler, so lets make two files. Lets create one name index.html for the HTML file and styles.css for the CSS one.

___


lets start building out the index.html. first we need to specify what kind of doc it is, add a head, and then the body.

{% highlight HTML %}
<!DOCTYPE html>
<html>
	<head>
		<title>HTML Demo</title>
		<!-- Your style.css goes here -->
	</head>
	<body>
		<!-- Place your code in here! -->
	</body>
</html>
{% endhighlight %}

So now that we got our HTML set up lets learn some basic tags! We will start by placing these in out body tag.

{% highlight HTML %}
<!-- <h1> is the opening tag -->
<!-- Your content will go between these tags -->
<!-- </h1> will close the tag -->
<h1>This is a heading 1</h1>
<h2>This is a heading 2</h2>
<h3>This is a heading 3</h3>
<h4>This is a heading 4</h4>
<h5>This is a heading 5</h5>
<h6>This is a heading 6</h6>
<p>This is a paragraph</p>
{% endhighlight %}

To see what it displays with you open your web browser just find your index.html file and double click it.

Tags can be given attributes. Attributes always needs a name and a value.

{% highlight HTML %}
<!-- This is an a tag with an attribute name of href, and the value is my blog --> 
<!-- site url this will create a link that will take the user to my website -->
<a href="https://taylorwu21.github.io/">My blog site</a>
{% endhighlight %}


Now lets create a simple list together. There are two different kinds of list an unorder list and order list.

{% highlight HTML %}
<!-- This is the unorder list-->
<ul>
	<!-- These are li tags they stand for listed item -->
	<li>Bullet Point 1</li>
	<li>Bullet Point 2</li>
	<li>Bullet Point 3</li>
</ul>

<!-- This is the Orderlist -->
<ol>
	<!-- li tags are always nested inside ul or ol tags -->
	<li>Listed Item 1</li>
	<li>Listed Item 2</li>
	<li>Listed Item 3</li>
</ol>
{% endhighlight %}

Lets step it up and create a table together. 

{% highlight HTML %}
<!-- open tag for a table -->
<table>
	<!-- tr = table row -->
	<tr>
		<!-- th = table head it means its the first row of the table -->
		<th>First Name</th>
		<th>Last Name</th>
		<th>Age</th>
	</tr>
	<tr>
		<!-- td = table data -->
		<td>Taylor</td>
		<td>Wu</td>
		<td>23</td>
	</tr>
<!-- closes the table -->
</table>
{% endhighlight %}


Now that we understand some HTML lets add our stylesheets to the head tag.

{% highlight HTML %}
<link rel="stylesheet" href="styles.css">
{% endhighlight %}

Before we start adding styling to the css file we need to learn how to use div, id, and class

{% highlight HTML %}
<!-- an id must be unique to a page -->
<div id="header">
	<h1>Hello World</h1>
	<p>This is part of an ID</p>
</div>

<!-- we can add classes to any tags we want -->
<div class="center-text">
	<h1>Hello World</h1>
	<p>I am learning about HTML and CSS</p>
</div>
{% endhighlight %}

Now to style them with css

{% highlight CSS %}
/* when styling an id you start with a '#' to notify your css that it is an id */
#header {
	font-size: 40px;
}

/* styling a class you would use a '.' */
.center-text {
	text-align: center;
}
{% endhighlight %}

Well hopefully you learned enough about HTML and CSS to start building a cool website!



