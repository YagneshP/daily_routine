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
 	************ callStack ***************

  | callStack |
  | --- |
	| outer() |
	| global()|      

  - Line 7 : first create "counter" variable and assign 0 value.
	- Line 8 : create "inner" variable and assign it to func defination of inner function. when this variable assigned it gets hidden property of *--scope--* which holds the "counter" variable.
	- Line 11 : *--now it return inner which holding inner function defination and "variable enviornment" "persist lexical scope reference data" like a backpack.  that means the data which is in local memory of the "outer" func.--*
	
	| Execution Context | local Memoery |
	| ------------------ | -------------- |
	| | counter: 0|
	| | inner: ->[fn]-> + [[scope]](backpack) |

 After completing outer func execution. outer() will pop out form call stack.
 	************ callStack ***************

  | callStack |
  | --- |
	|  |
	| global()| 

**Excuting myFunc**
- Line 15 : we are executing myFunc(); so thread of excution enter the "inner" which is on line 8
 - As in inner, the counter variable which is not stored in local memory of "inner" it will go to look for "counter" in so called backpack (hidden scope or P.L.S.R.D or Variable env.) and increment "counter" variable {{ counter : 1}}

 - Line 16 : Same process happen again and counter will increase to 2;

 **Notes**
 - You can't access the counter variable without running the inner func.
 - Counter variable wont get deleted as it is not stored in local memory.
 - The variable which is declared in outer and inner func doesn't reference it then it won't stored in backback. [memory leak] 