---
layout: post
title: "The Varying Variables of Ruby"
date: 2014-10-25 12:05:51 -0800
comments: true
categories: Ruby
---
<p>If you're at least a little familiar with ruby, or any programming language, you probably have an idea of what a variable is. Put <span class="italic">really</span> simply, it's the thing you assign values to. Values can be blocks of code but ultimately they are a string, number, boolean, or groups of any combination of these stored in an array or hash. Why use variables? Well there's many reasons but mainly it's so you don't have to write pieces of code over and over and over again. In today's entry we'll be going over the four main types of ruby variables and when to use them!</p>
<!-- more -->
<h3>#1 Local Variables</h3>

<p>The most common type you will see is the <span class="italic">local variable</span>. Local variable names start with a lowercase letter or underscore and can include any combination of letters, numbers and underscores. <span class="code">my_variable</span>, <span class="code">h_84hdfa_574</span>, <span class="code">_stuff</span> and <span class="code">x</span> are all examples of local variables. Assigning a value to a local variable looks like this:</p>

<pre class="code-window">example_variable = "Hello, world!"</pre>

<p>From the above example, our local variable is <span class="code">example_variable</span> to which we assign the string <span class="code">"Hello, world!"</span>. Local variables are only accessible within their scope. Understanding scope deserves it's own post, but for now you can think of it as a layer. When you start with a blank slate you are in the outermost layer, and adding things like classes, methods, or modules creates inner layers. A local variable defined in the <span class="italic">outer layer</span> can't be used by any of the inner layers. And a local variable defined inside a method can only be used in the method definition. Take a look at the following example to get a better idea of what I mean:</p>

<pre class="code-window">
var1 = "apple"

def make_apple_a_banana
  var1 = "banana"
end

make_apple_a_banana
puts var1</pre>

<p>Since we use the same variable name <span class="code">var1</span> you might expect our method <span class="code">make_apple_a_banana</span> to change the assignment of <span class="code">var1</span>. But as we just learned, even though these variables have the same name, they don't have the same scope. Therefore, running this code produces:</p>

<pre class="code-window">apple</pre>

<h3>#2 Global Variables</h3>

<p>Unlike local variables, <span class="italic">global variables</span> can be accessed by anything, anywhere in your program. You can recognize a global variable because it starts with a dollar sign <span class="code">$</span>. Ruby has built-in global variables and you can create your own. However, a lot of programmers will tell you that making global variables is rarely a good idea because they can contradict the object orientated nature of ruby. But for the sake of learning let's take a look at an example:</p>

<pre class="code-window">
$global_var = "Hello"

def world_greeting
  puts $global_var + " world!"
end

world_greeting

=>
Hello World!</pre>

<p>If we had instead used a local variable, running <span class="code">world_greeting</span> would have gave us an undefined variable or method error.</p>

<h3>#3 Instance Variables</h3>

<p><span class="ital">Instance variables</span> are variables that are accessible inside an object, but only that object. You'll usually use them in classes. Instance variable names always start with an at sign <span class="code">@</span>. Let's make a new class to show you an example:</p>

<pre class="code-window">
class Cup
  def initialize
    @full = false
  end

  def fill
    @full = true
  end

  def is_full?
    @full
  end
end

sippy_cup = Cup.new
sippy_cup.fill
sippy_cup.is_full?

=> true</pre>

<p>As you can see, our instance variable <span class="code">@full</span> can be used and manipulated in different method definitions within the class <span class="code">Cup</span>. Had we called <span class="code">@full</span> outside of our class, we would get an undefined variable error.</p>

<h3>#4 Class Variables</h3>

<p><span class="italic">Class variables</span> are kinda like global variables (and I use that comparison loosely) however they are scoped to their class hierarchy. They are designated by starting with two at signs <span class="code">@@</span>. They store values that are shared between a class and instances of that class, but they're not visible to any other objects. So they differ from global variables in that they are not mutable and visible everywhere. Let's look at an example to see what I mean:</p>

<pre class="code-window">
class Top
  def initialize(x)
    @@x = x
  end

  def get_x
    @@x
  end
end

class Middle < Top
end

class Bottom < Middle
end

top = Top.new("Hi!")
middle = Middle.new("Bye!")
bottom = Bottom.new("Hello?")
puts top.get_x
puts middle.get_x
puts bottom.get_x

=>
Hello?
Hello?
Hello?</pre>

<p>Uh oh! If you didn't know how class variables worked you might have expected three different outputs, but each time we created a class, we redefined <span class="code">@@x</span>. So <span class="code">puts</span>ing each of our objects gave us the last initialization <span class="code">"Hello?"</span>.</p>

<p>There you have it, four different types of ruby variables to play with! Now get busy and go practice already!</p>