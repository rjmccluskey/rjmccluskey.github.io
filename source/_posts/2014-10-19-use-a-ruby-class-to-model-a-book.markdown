---
layout: post
title: "Use a Ruby class to model a book!"
date: 2014-10-19 11:33:18 -0800
comments: true
categories: Ruby
---
<p>This week at <a href="http://devbootcamp.com">DBC</a> we learned how to create our own ruby classes. There's all kinds of classes already built into ruby, such as <span class="code">Integer</span>, <span class="code">Array</span>, and even <span class="code">Object</span>. Everything in ruby is an object and all objects are <span class="italic">instances</span> of a class. And just like how you can create your own objects, you can create your own classes too! In today's entry, I will be showing you how to create a class to model a book!</p>
<!-- more -->
<p>There's a lot we could put into our <span class="code">Book</span> class, but let's just say that you want to model the total number of pages in your book, what page you are on, the ability to turn pages, and the ability to go to a specific page. The following code can be used to create our class with these functions:</p>

<pre class="code-window">
 1     class Book
 2       def initialize(total_pages)
 3         raise ArgumentError.new("Please enter an Integer") if not total_pages.is_a? Integer
 4         @total_pages = total_pages
 5         @page = 1
 6       end
 7
 8       def page
 9         @page
10       end
11
12       def page=(page)
13         @page = page
14       end
15
16       def turn_page
17         @page += 1
18       end
19     end
    </pre>

<p>Now let's go over what this all means. First, we create the class simply with <span class="code">class Book</span>. When you make a class, you then define methods that are specific to those class objects. These are called, <span class="italic">class instance methods</span>. In other words, these methods are <span class="italic">instances</span> of the class and only objects that are instances of that class can use them. We create our first instance method on line 2. The method <span class="code">initialize</span> is a special instance method that runs when we create a new class object. We can create a new book called <span class="code">my_book</span> like so:</p>

<pre class="code-window">my_book = Book.new(200)</pre>

<p>Going back to our code, you can see that <span class="code">initialize</span> takes one argument <spane class="code">total_pages</spane>. When we created <span class="code">my_book</span> it takes <span class="code">200</span> as the argument for <span class="code">initialize</span>. Line 3 will raise an <span class="code">ArgumentError</span> if we enter anything other than an <span class="code">Integer</span> when we create the <span class="code">Book</span>. In line 4, we create the <span class="italic">instance variable</span> <span class="code">@total_pages</span> and set it equal to our argument <span class="code">total_pages</span>. Instance variables are extremely important when creating a class because they can be called outside of an instance method's definition. Line 5 creates another instance variable <span class="code">@page</span> and gives it a value of <span class="code">1</span>. When we make a new <span class="code">Book</span> object, we are automatically on page 1!</p>

<p>Our next instance method <span class="code">page</span> is created on line 8. This simply returns the value of the instance variable <span class="code">@page</span>. So if we wanted to see what page we were on in <span class="code">my_book</span> we could do it like this:</p>

<pre class="code-window">
my_book.page
=> 1 </pre>

<p><span class="code">#page</span> is called a <span class="italic">reader method</span> because it reads the value of an instance variable. We can also make <span class="italic">writer methods</span> that will change the value of an instance variable. This is exactly what we do on line 12! We can change to any page number we want like so:</p>

<pre class="code-window">my_book.page = 45
=> @page = 45</pre>

<p>You notice how we added spaces to the <span class="code">=</span> and we didn't need the parentheses? This is some <span class="italic">syntax sugar</span> that ruby lets us do! Lastly, on line 16 we define our instance method to turn pages. As you can see, this method will add <span class="code">1</span> to <span class="code">@page</span>. As you probably guessed you call it like this:</p>

<pre class="code-window">my_book.turn_page
=> @page = 46</pre>

<p>There you have it! Our very own ruby class just for books! Obviously, there's a lot more we could add to this class definition. What if you want to turn pages the other way? What if we turn to a page that is greater than our total pages? What's the name of the book? If you want some practice, try to go and add these on your own! But before I let you go there's one last thing I want to tell you about. Remember those reader and writer methods? They are super common when making classes. In fact, they are so common that there is a shorthand way of creating them. We use <span class="italic">attribute methods</span> to do this! Our code can be refactored to the following with the <span class="code">attr_accessor</span> method:</p>

<pre class="code-window">
 1     class Book
 2       attr_accessor :page
 3
 4       def initialize(total_pages)
 5         raise ArgumentError.new("Please enter an Integer") if not total_pages.is_a? Integer
 6         @total_pages = total_pages
 7         @page = 1
 8       end
 9
10       def turn_page
11         @page += 1
12       end
13     end
</pre>

<p>If we had just wanted to make a reader method we could have used <span class="code">attr_reader</span> and if we wanted to just make a writer method we could have used <span class="code">attr_writer</span>.</p>