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

| Execution Context | Global Memoery |
| ------------------ | -------------- |
| | outer: ->[fn]->|

- line 14 : we are not executing the function outer so the JS engine move to line 14 where we are executing the func.
  - here, in global memory will define variable "myFunc" and assign  it to result of outer();
	- thread execution will excute the outer function now;

	| Execution Context | Global Memoery |
	| ------------------ | -------------- |
	| | outer: ->[fn]->|
	| | myFunc: --- |
 
 **excuting outer fun**                      
  ***************************
  
	| Execution Context | Global Memoery |
	| ------------------ | -------------- |
	| | outer: ->[fn]->|
	|  | myFunc: --- |

	****************************
	
	************ callStack ***************
	
  | callStack |
  | -- |
	| outer() |
	| global()|

