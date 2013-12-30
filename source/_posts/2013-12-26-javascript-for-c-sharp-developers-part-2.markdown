---
layout: post
title: "Javascript for C# developers Part 2"
date: 2013-12-26 23:00:58 +0530
comments: true
sharing: false
categories: "javascript, C#"
keywords: "javascript for c# developer, switching from C# to javascript, javascript, Learn javascript, javascript vs c#, javascript functions, javascript inheritance, javascript prototype"
description: "Javascript for C# developers: Javascript functions and Closure explained"
---

Javascript functions
--------------------

The concept of functions in Javascript is different from C#, functions are not just sub-routines or methods here, it is the heart and soul of javascript, it acts as sub-routines as well as objects. We can assign functions to variables, pass a function as parameter of another function etc.. 
   
####Function parameters & Return values
Just like C# we can define function parameters and can pass values when we call it. The difference is, it is not necessary to pass the exact number of parameters that we defined in the function definition when we call it. We can call the function with more or less parameters that is defined. <!--more-->The parameters that are not passed in are just *undefined*. We can also access the function parameter values using the *arguments* object inside the function. Let's look at an example.
```
var displayName(name1, name2, name3){
	alert(name1);
	alert(name2);
	alert(name3);
}

displayName('John'); //name2 and name3 will be undefined
displayName('John, 'Mary'); ////name3 will be undefined

//Accessing parameters with arguments object
var displayName(name1, name2){
	alert(arguments.length); //Display the number of parameters passed
    alert(arguments[0]); //Display the first parameter
}

```
There is no **function overloading** in Javascript. There will be only one function with the specific name. If we define two functions with the same name and different argument lists. The second one will overwrite the first one regardless of the number of parameters. We will using the flexibility of javascript functions to achieve what we do with function overloading in C#. As is mentioned above, we can call a javascript function with more or less parameters that is defined. So, to achive function overloading kind of effect, inside the function definition we will check which all parameters are defined by the caller, and can prepare our logic according to that.   

Every javascript function returns a value. There is no way to specify a return type. As javascript is a dynamic language the return type will only be resolved at the runtime. If we haven't specified any return, the returned value will be of type *undefined*. Functions can return values as well as reference to other functions.   

Scoping
-------
Unlike in C#, JavaScript does not have block-level scope (variables scoped to surrounding curly brackets). for example, in C# if we define a variable inside an if statement or a for loop it is not available outside it, because it is local to where it is defined. In javascript curly braces dont limit the scope, the only thing that creates a scope in javascript is a function. Variables declared within a function are local variables and are only accessible within that function or by functions inside that function. Here is an example code.

{% codeblock C# %}
var x = 10;
if(true)
{
	var y = 5 * x;
}
var result = y; // variable y is not available here
{% endcodeblock %}

{% codeblock Javascript %}
var x = 10;
if(true){
	var y = 5 * x;
}
var result = y; // This works!

//Creating scope with functions
var x = 10;
function hello(){
	var y = 5 * x;
}
var result = y; // This won't work.
{% endcodeblock %}   

Closure 
-------
A closure in JavaScript is like keeping a copy of the all the local variables, just as they were when a function exited. If you declare a function within another function, then the local variables can remain accessible after returning from the function you called. The following code returns a reference to a function:
{% codeblock Javascript %}
function sayHello2(name) {
    var text = 'Hello ' + name; // Local variable
    var sayAlert = function() { alert(text); }
    return sayAlert;
}
say2 = sayHello2('Bob');
say2(); // alerts "Hello Bob"
{% endcodeblock %}  

If we invoke the function reference returned by *sayHello2* function, you can see the local variable 'text' of *sayHello2* function is still available with the *sayAlert* function. 


