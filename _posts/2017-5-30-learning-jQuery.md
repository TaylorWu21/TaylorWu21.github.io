---
layout: post
title: "jQuery Calculator"
date: 2017-5-25 14:11:00
category: jQuery
---
<p>
  jQuery is a javascript library that makes it easier for event handling.
</p>

<br />

<p>
  I created a calculator with jQuery to help students at dpl understand the power of jQuery.
</p>

<h1>Why use jQuery?</h1>
<hr/>
* jQuery is a javascript library that makes event handling a lot easier
* It has many helper function we can use to make manipulating the DOM

<p>Here's a link to see all the jQuery documentation</p>
<a href='http://api.jquery.com/'>jQuery Documentation</a>

<h1>Basic jQuery Syntax</h1>
* First we need to call on the jQuery libraru with a '$'
* Then we use the element selector. We can get the element tag, id, or class
* Then we can call any jQuery methods we want on it.
<p>Here's how it looks</p>
* $('SELECTED_ELEMENT').METHOD()
<p>Selecting with Element tag</p>
* $('h1')
<p>Selecting with an id</p>
* $('#header')
<p>Selecing with a class</p>
* $('.btn')

<h4>With jquery we can grab elements with less syntax as vanilla javascript</h4>

<p>vanilla js way of getting element</p>
* var numberButtons = getElementsByClassName('number_button');

<p>jQuery variables usually starts with a '$'. It will return an array with the same class name</p>
* var $numberButtons = $('.number_button')</p>
<p>this will return an array of all html elements with the 'number_button' class</p>
* $('.number_button');

<h4>Now that we understand the basic syntax of jQuery lets build the calculator</h4>

<style>
  .btn {
  margin: 5px;
  }

  h3 {
    height: 20px;
  }
  .jumbotron {
    padding-top: 30px;
    padding-bottom: 30px;
    margin-bottom: 30px;
    color: inherit;
    background-color: #eee;
  }
</style>

<h1 id='header' class='center'>jQuery Calculator</h1>
<div class="jumbotron">
  <h3 id='output' class='center'></h3>
</div>
<div class='row'>
  <div class='col s3 offset-s9 center'>
    <button id='clear_button' class='btn btn-large red'>C</button>
  </div>
</div>
<div class='row'>
  <div class='col s3 center'>
    <button class='btn btn-large blue number_button'>1</button>
  </div>
  <div class='col s3 center'>
    <button class='btn btn-large blue number_button'>2</button>
  </div>
  <div class='col s3 center'>
    <button class='btn btn-large blue number_button'>3</button>
  </div>
  <div class='col s3 center'>
    <button class='btn btn-large green operator_button'>+</button>
  </div>
</div>
<div class='row'>
  <div class='col s3 center'>
    <button class='btn btn-large blue number_button'>4</button>
  </div>
  <div class='col s3 center'>
    <button class='btn btn-large blue number_button'>5</button>
  </div>
  <div class='col s3 center'>
    <button class='btn btn-large blue number_button'>6</button>
  </div>
  <div class='col s3 center'>
    <button class='btn btn-large green operator_button'>-</button>
  </div>
</div>
<div class='row'>
  <div class='col s3 center'>
    <button class='btn btn-large blue number_button'>7</button>
  </div>
  <div class='col s3 center'>
    <button class='btn btn-large blue number_button'>8</button>
  </div>
  <div class='col s3 center'>
    <button class='btn btn-large blue number_button'>9</button>
  </div>
  <div class='col s3 center'>
    <button class='btn btn-large green operator_button'>x</button>
  </div>
</div>
<div class='row'>
  <div class='col s3 center'>
    <button class='btn btn-large number_button'>.</button>
  </div>
  <div class='col s3 center'>
    <button class='btn btn-large blue number_button'>0</button>
  </div>
  <div class='col s3 center'>
    <button id='equal_button' class='btn btn-large btn-success'>=</button>
  </div>
  <div class='col s3 center'>
    <button class='btn btn-large green operator_button'>/</button>
  </div>
</div>

<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
<script type='text/javascript'>

$(document).ready(function() {
  // We need variables to save our numbers and operators
  var leftNumber = '';
  var rightNumber = '';
  var operator = '';
  var result = '';

  // Now we need to check when a user clicks a number
  $('.number_button').click( function() {
    // check if the user has selected on operator yet
    if(operator) {
      rightNumber += this.innerText;
    } else {
      leftNumber += this.innerText;
    }

    setScreen(leftNumber + ' ' + operator + ' ' + rightNumber);
    // console.log('right Number', rightNumber);
    // console.log('left number', leftNumber);
  });

  // Here we check which operator button they clicked
  $('.operator_button').click( function() {
    // console.log(this.innerText);
    operator = this.innerText;
    setScreen(leftNumber + ' ' + operator)
  });

  // Check when they press the equal button
  $('#equal_button').click( function() {
    // console.log(leftNumber);
    // console.log(operator);
    // console.log(rightNumber);
    var firstNum = parseFloat(leftNumber);
    var secondNum = parseFloat(rightNumber);
    console.log(operator)
    if(leftNumber && operator && rightNumber) {
      switch(operator) {
        case '+':
          result = firstNum + secondNum;
          break;
        case '-':
          result = firstNum - secondNum;
          break;
        case 'X':
          result = firstNum * secondNum;
          break;
        case '/':
          result = firstNum / secondNum;
          break;
        if(secondNum === 0) {
          result = 'Cannot Divide By 0. Please Clear and try again';
        }
        break;
      }
    } else {
      result = 'Invalid Operation Clear and Try Again.'
    }
    setScreen(result)
    // set result to the first number and clears the second, so user can keep computing
    leftNumber = result;
    rightNumber = '';
  });

  // Clear everything out when user clicks it
  $('#clear_button').click( function() {
    leftNumber = '';
    rightNumber = '';
    operator = '';
    setScreen('');
  });

  function setScreen(answer) {
    // using jQuery to get my output div
    // .text() is a jQuery method that takes in an argument and will display it to the innerText
    $('#output').text(answer)
  }
});
</script>

<h2>HTML Code</h2>

<hr />

{% highlight html %}
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/materialize/0.98.2/css/materialize.min.css">

  <h1 id='header' class='center'>jQuery Calculator</h1>
  <div class="jumbotron">
    <h3 id='output' class='center'></h3>
  </div>
  <div class='row'>
    <div class='col s3 offset-s9 center'>
      <button id='clear_button' class='btn btn-large red'>C</button>
    </div>
  </div>
  <div class='row'>
    <div class='col s3 center'>
      <button class='btn btn-large blue number_button'>1</button>
    </div>
    <div class='col s3 center'>
      <button class='btn btn-large blue number_button'>2</button>
    </div>
    <div class='col s3 center'>
      <button class='btn btn-large blue number_button'>3</button>
    </div>
    <div class='col s3 center'>
      <button class='btn btn-large green operator_button'>+</button>
    </div>
  </div>
  <div class='row'>
    <div class='col s3 center'>
      <button class='btn btn-large blue number_button'>4</button>
    </div>
    <div class='col s3 center'>
      <button class='btn btn-large blue number_button'>5</button>
    </div>
    <div class='col s3 center'>
      <button class='btn btn-large blue number_button'>6</button>
    </div>
    <div class='col s3 center'>
      <button class='btn btn-large green operator_button'>-</button>
    </div>
  </div>
  <div class='row'>
    <div class='col s3 center'>
      <button class='btn btn-large blue number_button'>7</button>
    </div>
    <div class='col s3 center'>
      <button class='btn btn-large blue number_button'>8</button>
    </div>
    <div class='col s3 center'>
      <button class='btn btn-large blue number_button'>9</button>
    </div>
    <div class='col s3 center'>
      <button class='btn btn-large green operator_button'>x</button>
    </div>
  </div>
  <div class='row'>
    <div class='col s3 center'>
      <button class='btn btn-large number_button'>.</button>
    </div>
    <div class='col s3 center'>
      <button class='btn btn-large blue number_button'>0</button>
    </div>
    <div class='col s3 center'>
      <button id='equal_button' class='btn btn-large btn-success'>=</button>
    </div>
    <div class='col s3 center'>
      <button class='btn btn-large green operator_button'>/</button>
    </div>
  </div>
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
{% endhighlight %}

<br />

<h2>Javascript Code</h2>
<hr />
{% highlight javascript %}
  // need to wrap the whole thing in a document.ready because we want everything in the DOM to load before adding
  // event handlers to them
  $(document).ready(function() {
    // We need variables to save our numbers and operators
    var leftNumber = '';
    var rightNumber = '';
    var operator = '';
    var result = '';

    // Now we need to check when a user clicks a number
    $('.number_button').click( function() {
      // check if the user has selected on operator yet
      if(operator) {
        rightNumber += this.innerText;
      } else {
        leftNumber += this.innerText;
      }

      setScreen(leftNumber + ' ' + operator + ' ' + rightNumber);
      // console.log('right Number', rightNumber);
      // console.log('left number', leftNumber);
    });

    // Here we check which operator button they clicked
    $('.operator_button').click( function() {
      // console.log(this.innerText);
      operator = this.innerText;
      setScreen(leftNumber + ' ' + operator)
    });

    // Check when they press the equal button
    $('#equal_button').click( function() {
      // console.log(leftNumber);
      // console.log(operator);
      // console.log(rightNumber);
      var firstNum = parseFloat(leftNumber);
      var secondNum = parseFloat(rightNumber);

      if(leftNumber && operator && rightNumber) {
        switch(operator) {
          case '+':
          result = firstNum + secondNum;
          break;
          case '-':
          result = firstNum - secondNum;
          break;
          case 'x':
          result = firstNum * secondNum;
          break;
          case '/':
          result = firstNum / secondNum;
          if(secondNum === 0) {
            result = 'Cannot Divide By 0. Please Clear and try again';
          }
          break;
        }
      } else {
        result = 'Invalid Operation Clear and Try Again.'
      }
      setScreen(result)
      // set result to the first number and clears the second, so user can keep computing
      leftNumber = result;
      rightNumber = '';
    });

    // Clear everything out when user clicks it
    $('#clear_button').click( function() {
      leftNumber = '';
      rightNumber = '';
      operator = '';
      setScreen('');
    });

    function setScreen(answer) {
      // using jQuery to get my output div
      // .text() is a jQuery method that takes in an argument and will display it to the innerText
      $('#output').text(answer)
    }
  });
{% endhighlight %}

<p>jQuery is a powerful library for manipulating the DOM. I hope you guys enjoyed reading this blog post!</p>