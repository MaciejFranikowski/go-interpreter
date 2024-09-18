# go-interpreter

This is an interpreter for a made up programming language - Monkey.
Here it's list of features:
• C-like syntax
• variable bindings
• integers and booleans
• arithmetic expressions
• built-in functions
• first-class and higher-order functions • closures
• a string data structure
• an array data structure
• a hash data structure

## Monkey value binding
```
let age = 1;
let name = "Monkey";
let result = 10 * (20 / 2);
```

## Monkey array creation
```
let myArray = [1, 2, 3, 4, 5];
let thorsten = {"name": "Thorsten", "age": 28};
myArray[0] // => 1 
thorsten["name"] // => "Thorsten"
```

## Monkey functions

```
// small function
let add = fn(a, b) { return a + b; };

// implicit return
let add = fn(a, b) { a + b; };

// calling a function
add(1, 2);

// recursive functions
let fibonacci = fn(x) { 
	if (x == 0) {
		0
	} else {
		if (x == 1) {
			1
		} else {
			fibonacci(x - 1) + fibonacci(x - 2);
		}
	}
};

// higher order functions (functions that take functions as arguments)
let twice = fn(f, x) { 
	return f(f(x));
};
let addTwo = fn(x) { 
	return x + 2;
};
twice(addTwo, 2); // => 6
```
Yes, we can use functions as arguments in function calls. Functions in Monkey are just values, like integers or strings. That feature is called “first class functions”.

## Interprerter parts
• the lexer
• the parser
• the Abstract Syntax Tree (AST) • the internal object system
• the evaluator