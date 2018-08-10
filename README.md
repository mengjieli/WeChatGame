
如果觉得代码库太大，可以参考我以前写的表达式分析算法的文章
https://blog.csdn.net/jiexiaopei_2004/article/details/41546673


include Binding.js

support type :
```number,bool,string,var```

support operate ：
```+ - * /  %  !   <<  >>  >>>  >  <   >=  <=  ==  ===  !==  !=   &   ~  ^   |   &&  ||   ?:    ()```

### Examples

1. simple expr
```js
console.log(binding.eval("(1 + 2) * 4 / 2")); //console 6
```

2. expr with var
```js
var v0 = 3;
console.log(binding.eval("$0 * 4",[v0])); //console 12
```
3. expr with var and function
```js
var v0 = 3;
var v1 = 6;
console.log(binding.eval("Math.sqrt($0 * 3 * $1 * 6)",[v0,v1])); //console 18
```
4. expr with var and self-define function
```js
var v0 = 9;
var addFunction = function(a,b) {
    return a + b;
}
console.log(binding.eval("add(Math.sqrt($0), 2)",[v0],{add:addFunction})); //console 5
```
5. 3 op expr
```js
console.log(binding.eval("3 > 2 ? true : false")); //console true
```
when this project receive 100 star,i will support define var in the script, and so on.

