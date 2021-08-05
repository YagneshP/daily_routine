### Types system (first piller)

#### Primitive types

```js 
typeof (function a(){console.log('hi')}) // "function" 
```

- 'NaN' is not equal to itself 
- isNaN utility first coerce the value into Number and then check. 
- While Number.isNaN just check before coerce.
- typeof(NaN) is "number"
