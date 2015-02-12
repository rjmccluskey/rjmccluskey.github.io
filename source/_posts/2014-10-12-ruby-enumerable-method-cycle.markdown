---
layout: post
title: "Ruby Enumerable Method: #cycle"
date: 2014-10-12 11:05:59 -0800
comments: true
categories: [Ruby, Enumerables]
---
<p>I've been getting my hands dirty with algorithms this week and consequently I've been looking at built-in Ruby methods. Lots and lots of methods. It was a little daunting to see the massive lists of these methods on <a href="http://ruby-doc.org/core-2.1.3/index.html">Ruby Docs</a> but I am finally feeling less intimidated by them. I'm not even close to knowing all of them, but I've gotten pretty good with some of them. So guess what?! I'm going to teach you about the enumerable method, <a href="http://ruby-doc.org/core-2.1.3/Enumerable.html#method-i-cycle"><span class="code">#cycle</span></a>.</p>
<!-- more -->
<p>From <a href="http://ruby-doc.org/core-2.1.3/index.html">Ruby Docs</a>, the enumerable method <span class="code">#cycle</span> has the following syntax:</p>

<pre class="code-window">
  cycle(n=nil) { |obj| block }  ---> nil <br>
  cycle(n=nil)  ---> an_enumerator
</pre>

<p><span class="code">#cycle</span> takes one argument (shown as <span class ="code">n</span> in the above syntax) and calls <span class="code">block</span> for each element of enum repeatedly <span class ="code">n</span> times, or forever if none or <span class="code">nil</span> is given. If a non-positive number is given, it doesn't do anything. If the loop finishes without being interrupted, it returns <span class="code">nil</span>. Also, <span class="code">#cycle</span> is a non-destructive method, meaning that it will not alter the object we call it on. If no <span class="code">block</span> is given, it returns an enumerator instead.</p>

<p>So the best way to understand how to use a new method is with some examples! Let's print a grocery list 3 times so that we don't forget what to buy.</p>

<pre class="code-window">
  grocery_list = ["milk","eggs","bread","salsa"] <br>
  grocery_list.cycle(3) { |item| print item + " " } <br>
  => milk eggs bread salsa milk eggs bread salsa milk eggs bread salsa
</pre>

<p>So there you have it! My quick little guide to how to use the enumerable method <span class="code">#cycle</span>. Get out there and try it for yourself!</p>