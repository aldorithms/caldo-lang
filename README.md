# Caldo-lang
Documentation for the Caldo Programming Language

## What is Caldo?

Caldo will be a object-oriented/class-based compiled programming language syntaxically based on modern languages like Go, V, and Rust.
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

let bar := value; // will assume
```
#### Primitives
Caldo-lang has 15 primitive data types, including 5 unsigned integers, 4 signed integers, 2 floating points, 3 character types, and a boolean type.
These are: ``u0``, ``u8``, ``u16``, ``u32``, ``u64``, ``i8``, ``i16``, ``i32``, ``i64``, ``f32``, ``f64``, ``c8``, ``c16``, ``c32``, & ``bool``.

##### Integers
This is a basic declaration for a 64-bit unsigned integer.
```
let foo be u64 = 563345; //let foo be a 64-bit unsigned integer equal to 563345;
```
By default, integers will be unsigned. There is no default size, rather the size will be determined by the value of the variable in order to use up the least amount of space.
```
let foo be = 255; //Since 255 < 2^8, foo will be type u8;
let bar := 65540; //Since 65540 > 2^16, bar will be type u32;
```
##### Floating 


### Functions
I originally did not want to use function declarations ``fn`` because I felt they were just bloatware.
In assembly, subroutines and global variables are declared the same way.
Therefore, it seemed silly to add more work for the compiler.
However, I also felt this might be difficult for new users to pick-up, so I kept this feature in.

```
fn function(arguments
{
	statements;
}
```
### Object-Orientation
#### Tuples
```
let foo be tuple = 
{  
	let x be i32 = 45;
	let msg be str = "Hi mom!\n";
}
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
	let msg be str = "Hello World!\n";
};
let bar be str = foo.msg;
```
You can also nest objects inside of objects.
```
let foo be obj =
{
	let msg be obj =
	{
		let Hello be str = "Hello World!\n";
		let Bye be str = "Goodbye!\n";
	};
};
let bar be str = foo.msg.Hello;
```
The object's methods are declared using the standard function declaration, within the ``{ }`` brackets.
To access member attributes inside method, user ``this.``
```
let foo be obj =
{
	let msg be str = "Hello World!\n";
	fn sayHello()
	{
		print(this.msg)
	}
};
foo.sayHello()
```
#### Structures
A ``struct`` is a template object that can only contain member attributes.
You can think of a ``tuple`` as an instance of a ``struct``.
For this reason, member attributes cannot be assigned a value during structure declaration.
```
struct myStruct
{
	i8 x;
	u16 y;
	f32 z;
}
```
Once a ``struct`` is declared, it becomes another datatype, declared like this:
```
let foo be myStruct = { x = 45, y = 576, z = 894.0 };
```
Unlike in C++, even ``struct`` can inherit, using the ``ext`` keyword followed by the parent structure.
```
struct Parent
{
	i8 x;
	u16 y;
	f32 z;
}

strict myStruct ext Parent
{
	c8 a;
}

let foo be myStruct = { x = -45, y = 454, z = 894.0, a = 'd' };
```
#### Classes
A ``class`` is like a ``struct`` that may contain member methods.
```
class myClass
{
	myClass();
	~myClass();
}
```
Declare an instance of a ``class`` like this:
```
let foo be myClass = myClass();
let bar be myClass(foo);
```
or like this:
```
let foo := myClass();
let bar := myClass(foo);
```
