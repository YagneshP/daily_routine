## Closures fundamentals


- Like we have a function which has another function in it and we retun that/(inner)/ function
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
| | outer: ->[fn]->|
