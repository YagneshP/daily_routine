## Closures fundamentals


-  we have a function which has another function in it and we retun that (inner) function
```js
function outer () {
	let counter = 0;
	function inner(){
		counter++;
	};
	return inner
};

const myFunc = outer();
myFunc(); // what will happen here
myFunc(); 
```

#### *Process*

- Line 6 : in Global memory define "outer" with "function defination"
| Global Memoery |
| -------------- |
| outer: ->[fn]->|

- line 14 : we are not executing the function outer so the JS engine move to line 14 where we are executing the func.
  - here, in global memory will define variable "myFunc" and assign  it to result of outer();
	- thread execution will excute the outer function now;

	| Global Memoery |
	| -------------- |
	| outer: ->[fn]->|
	| myFunc: --- |
 
 **excuting outer fun**   
 this  willl create new execution context for outer fun                   
  - first create "counter" variable and assign 0 value.
	- create "inner" variable and assign it to func defination of inner function.
	- now it return inner which holding inner function defination and "variable enviornment" "persist lexical scope reference data" like a backpack.  that means the data which is in local memory of the "outer" func.
	| Execution Context | local Memoery |
	| ------------------ | -------------- |
	| | counter: 0|
	| | inner: ->[fn]-> |

	************ callStack ***************

  | callStack |
  | --- |
	| outer() |
	| global()|

