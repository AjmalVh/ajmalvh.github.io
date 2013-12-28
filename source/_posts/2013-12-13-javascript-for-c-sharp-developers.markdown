---
layout: post
title: "Javascript for C# developers Part 1"
date: 2013-12-25 22:31:02 +0530
comments: true
sharing: false
categories: "javascript, C#"
keywords: "javascript for c# developer, javascript, C#, Learn javascript, javascript vs c#, javascript vs c sharp"
description: "Javascript for C# developers: Javascript basics in C# point of view"
---


## Introduction
Javascript is the new emerging language, few years back we where using it only on client side, now javascript is everywhere, there are tons of client side and server side frameworks.   
   
I am C# developer for past few years, now i am working in with javascript also. When a developer from any curly brace language learn javascript, seeing the syntax, they just assume that the language works in the same way, but it is not. Even though the language syntax have some similarities it won't necessarily works in the way as you expected. Here are some tips that would help you to learn javascript from a C# developers point of view. <!--more-->

##Comparing the languages
Even though C# and Javascript are similar in structure, when we get down we can see a lot of differences in how they works. Here are some of the C# conventions and their javascript equivalent

Strongly Typed => Loosely Typed   
Static => Dynamic   
Classical Inheritance => Prototypical Inheritance   
Classes => Functions   
Methods => Functions   
   
####Strong Typing vs Loose Typing   
In strong typing, types are defined by names and have a static structure, we know what all properties and 
methods are inside a specific type. We cannot assign properties or methods dynamically at the runtime.
   
```
//C#
var foo = 123;

foo = new Person(); //Compiler Error
foo = "Hey"; //Compiler Error

//Javascript
var bar = 123;

bar = "Hey Ajmal"; //Now bar is of type string
bar = new Person() //Now bar holds the person object
```

In C#, we know the type of object returned in the compile time itself, but this is not in the case of javascript, type is assigned in the runtime just like C# the 'dynamic' keyword in C#. Do not confuse javascript var keyword with the var keyword in C#. In C# we can use var when the compiler can infer the type in the compile time itself. In the above example, we cannot re-assign the type of variable 'foo' to onother type in C#, because we typed 'foo' to be an integer and we have to consistently use this as an integer, we cannot change the type of a variable after its creation. In Javascript there is no such rules.   
   
####Dynamic Typing  
In Javascript we can add on to and remove properties of an object any time you need. Here we have an object with two properties, we can add properties or change the type of existing ones any time.
```
var person = {
	name: "Ajmal",
	age: 24
};

person.country = "India";
person.age = "Twenty four";
person.sayName = function() {
	alert("My name is "+ this.name);
}
```
This is a very powerful feature of javascript, but there is a chance to mess up the code if we don't use it properly.   

Primitive Types
--------------
These are the basic types in Javascript.   

*	boolean
*	number
*	string
*	object
*	function
*	null
*	undefined

The types boolean, number, string and null has the same concept we have in C#. 'undefined' is a special type in javascript, it implies the variable has not been defined yet. The concept of function in Javascript is different from C#, lets discuss about it in the coming chapters.