# Caldo-lang
Documentation for the Caldo Programming Language

## What is Caldo?

Caldo will be a compiled programming language syntaxically based on modern languages like Go, V, and Rust.
Caldo will aim to be much more mneumonic than other languages, to reduce the learning curve for users.

## Introduction

### Boilerplate
So to start off, the default Caldo-Lang entry point will be ``main`` , like in most compiled languages.
The typing structure will be very familiar to most programmers who have done anything related to the C Language.
Declare the main function with ``fn main()``, followed by two brackets ``{ }`` which can be spaced out however you like.
In between the two brackets, you will type statements procedurally. Each statement is ended with a semi-colon ``;``.
```
fn main()
{
	statement;
}
```
The ``main`` function has a return type of ``u0`` by default, roughly similar to void. This was adapted from TempleOS's HolyC language.
There is no need, nor harm in declaring the ``main`` function's return type, as so.
```
fn main() u0
{
	ret u0;
}
```
### Variables
This is what the structure of a normal variable declaration will look like.
```
let foo be <type> = value;
```
#### Primitives

```
let foo be = 
```
#### Simple Objects
A simple object can be declared with the data type ``obj``.

```
let foo be obj = { };
```
The object's attributes can be declared using the standard variable declaration, within the ``{ }`` brackets
```
let foo be obj = 
{
	let this.msg be str = "Hello World!\n";
};
let bar be str = foo.msg;
```
You can also nest objects inside of objects.
```
let foo be obj =
{
	let this.msg be obj =
	{
		let this.Hello be str = "Hello World!\n";
		let this.Bye be str = "Goodbye!\n";
	};
};

let bar be str = foo.msg.Hello;
```
### Functions
I originally did not want to use function declarations ``fn`` because I felt they were just bloatware.
In assembly, subroutines and global variables are declared the same way.
Therefore, it seemed silly to add more work for the compiler.
However, I also felt this might be difficult for new users to pick-up, so I kept this feature in.

```
fn function( <type> args 
```
