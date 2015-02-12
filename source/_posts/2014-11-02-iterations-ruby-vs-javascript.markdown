---
layout: post
title: "Iterations - Ruby vs JavaScript"
date: 2014-11-02 12:01:25 -0800
comments: true
categories: [Ruby, JavaScript]
---
<p>I've started learning JavaScript this week and I have mixed feelings about it. At first it was just a pain in the ass. I've gotten pretty used to the wonders of ruby and how simple it can be. JavaScript on the other hand, can be pretty tough for a beginner. But as I got going I started to really like it because it is really fun to manipulate HTML elements. Anyways, to show you a little comparison between ruby and JS let's take a look at how we can iterate through an array in both languages.</p>
<!-- more -->
<h3>Ruby</h3>

<p>If you are using ruby and you have an array object, you can do something to each of the values in that array using the <span class="code">each</span> method. If that's not straightforward I don't know what is! Let me show you how it works with an example:</p>

<pre class="code-window">
# Ruby

array = [1,2,3,4,5]
array.each { |value| puts value }

# 1
# 2
# 3
# 4
# 5</pre>

<p>This built in method knows how to cycle though the array automatically. Once you get used to the syntax there really isn't much to think about. Of course this is a simple example and it can get much more complicated but you get the idea.</p>

<h3>JavaScript</h3>

<p>Unfortunately, there is nothing built into JS to iterate as easy as we can in ruby. So far, the best way I've found to iterate as we did with the example above is by using a <span class="code">for</span> loop. Let's do the exact same iteration in JS:</p>

<pre class="code-window">
// JavaScript

var array = [1,2,3,4,5];
for (var count = 0; count < array.length; count++) {
  console.log(array[count]);
}

// 1
// 2
// 3
// 4
// 5</pre>

<p>A quick comparison shows that there's definitely a little more to think about when iterating in JS. Making our array is pretty similar except we use the keyword <span class="code">var</span> and we need a semi-colon at the end of the statement. Our <span class="code">for</span> loop takes three expressions. The first creates a new local variable <span class="code">count</span> and assigns an initial value of 0 to it. The second expression is used so that the loop knows when to stop. And the third expression adds 1 to <span class="code">count</span> after each loop. I think it's pretty obvious that ruby wins when it comes to ease of iterating.</p>