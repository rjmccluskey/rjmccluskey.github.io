---
layout: post
title: "Using Arrays and Hashes in Ruby"
date: 2014-10-05 13:06:11 -0800
comments: true
categories: Ruby
---
<p>Time for another coding lesson. So what's on the table for this week? Why, it's our good fiends <span class="italic">arrays</span> and <span class="italic">hashes</span>.</p>
<!-- more -->
<p>So what are they? Well, to put it simply, they are fancy variables that we can use to store lists of data. A normal, boring variable stores just one value. But with arrays and hashes we can store an endless amount! We can even use them to store other arrays and hashes! So why do we have two types and what are the differences between the two?</p>

<p>To give you an answer to that last question, let me first explain what arrays are. As you already know an array is a list of data. In ruby, you create an array with square brackets `[...]` and separate the values with commas. So for example if you wanted an array named <span class="italic">array</span> (I know, very creative right?!) containing three strings, "one" "two" and "three" you'd do so like this:</p>

```Ruby
array = ["one","two","three"]
```

<p>But there's something important to know about arrays. Each value in an array is assigned a number. This is important for when you want to call one of those values. But instead of starting with the number 1, the first value inside an array is assigned the number 0. So remember that super sweet array we just created? Well, the first value, "one", is assigned as 0, "two" is assigned as 1, and "three" is assigned as 2. So if you wanted to print the "first" value from your array to the screen, you'd do so like this:</p>

```Ruby
puts array[0]
```

<p>Arrays are great when you want order to your list. The order can be manipulated in all sorts of ways! A simple example would be a list of names that you want to then alphabetize. But what if you don't care so much about the order and you want to describe the values with something different than numbers? This is exactly where hashes come into play! With hashes, you can assign values with whatever you want. Hashes are lists of "key:value pairs". Keys must be unique but values can be repeated. So let's say you wanted to create a hash of people's names and their eye color. You could do it like this:</p>

```Ruby
eye_color = { Richard: "blue", Natalie: "green", Bob: "green" }
```

<p>As you can see, instead of the square brackets hashes use curly braces `{...}`. If you want to print Bob's eye color, you could do so like this: </p>

```Ruby
puts eye_color[:Bob]
```

<p>Calling a value from a hash uses square brackets just like an array, and make sure to put the colon ( : ) in front of the key. The order of hashes are a bit more arbitrary, but they are better than arrays to use in certain situations.</p>