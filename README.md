include Binding.js

### Examples

1. simple expr
```js
console.log(binding.eval("(1 + 2) * 4 / 2")); //console 6
```
<br/>
2. expr with var
```js
var v0 = 3;
console.log(binding.eval("$0 * 4",[v0])); //console 12
```
<br/>
3. expr with var and function
```js
var v0 = 3;
var v1 = 6;
console.log(binding.eval("Math.sqrt($0 * 3 * $1 * 6)",[v0,v1])); //console 18
```
<br/>
4. expr with var and self-define function
```js
var v0 = 9;
var addFunction = function(a,b) {
    return a + b;
}
console.log(binding.eval("add(Math.sqrt($0), 2)",[v0],{add:addFunction})); //console 5
```
<br/>
5. 3 op expr
```js
console.log(binding.eval("3 > 2 ? true : false")); //console true
```
<br/>
when this project receive 100 star,i will support define var in the script, and so on.