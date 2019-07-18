### 函数学习笔记

#### 1.arguments

**arguments** 是一个对应于传递给函数的参数的类数组对象。

```javascript
// arguments
function fn(a, b) {
  console.log(arguments);
  arguments[0] = 'wuwei';
  b = 'tianna';
  console.log(arguments[0]); //  arguments[0] 和a之间是有映射规则的,你变我也变
  console.log(arguments[1]);
  console.log(a, b)
}
fn(10, 30, 40, 50, 30);
```

```javascript
function fun(a, b) {
  // console.log(arguments)

  switch (arguments.length) {
    case 1:
      console.log(++a);
      break;
    case 2:
      console.log(a + b);
      break;
  }
}
```

### 2.函数返回值

 return  函数的返回值,默认的返回值是undefined
 碰到return 函数就结束了

```javascript
function fn(a, b) {
  // console.log(a + b);
  return (a + b);
}
var c = fn(10, 20);
console.log(c);
```

节流

```javascript
function fn(a) {
  if (a < 10) return
  console.log(1);
  console.log(2);
  console.log(3);
  console.log(1);
  console.log(2);
  console.log(3);
  console.log(1);
  console.log(2);
  console.log(3);

}

fn(12)
```

### 3.函数的另外一种定义方式--------函数表达式

```javascript
(有名函数表达式)(尽量不要用这种)
var fun = function fn(a, b) {

  return a + b;
}

console.log(fun())
```

```javascript
匿名函数表达式(尽量用这种)
var fun = function (a, b) {
  return a + b;
}

console.log(fun())
```

### 4.函数预解析-----函数声明会被提升

```javascript
// 先调用
 fun()

// 后定义
 function fun() {
  console.log('我是函数,我被执行了')
 }
```

函数表示是不会提升的,函数表示是不会提升的,注意是函数不会提升,前面的变量声明是会被提升

```javascript
var fun = function () {
  console.log('我是函数,我被执行了')
}
console.log(fun)
fun()
```

### 5.函数自执行--（  immediately-invoked function expression  ） 即时调用函数表达式

```javascript
function fun() {

}
fun()
```

我们要把函数声明降级 ,降为一个函数表达式

```javascript
(function fun(a) {
  console.log(a)
})(10);
```

或

```javascript
(function fun(a) {
  console.log(a)
}(10));
```

该函数执行得到a和b中较大值与c相加的结果

```javascript
function sum(a, b, c) {

  return (function (a, b) {
    return a > b ? a : b
  })(a,b) + c;
}

sum(4, 2, 3);   // 7
sum(2, 3, 5);   //8
```