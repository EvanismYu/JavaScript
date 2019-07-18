# JavaScript

### 1.==与===的区别：

```javascript
    1、=== ：称为等同符，当两边值的类型相同时，直接比较值，若类型不相同，直接返回false；
    2、== ：称为等值符，当等号两边的类型相同时，直接比较值是否相等，若不相同，则先转化为类型相同的值，再进行比较；

    类型转换规则：
         1）如果等号两边是boolean、string、number三者中任意两者进行比较时，优先转换为数字进行比较。
       2）如果等号两边出现了null或undefined,null和undefined除了和自己相等，就彼此相等

     注意：NaN==NaN  //返回false，NaN和所有值包括自己都不相等。
```

```javascript
console.log('8' == 8);	//true
console.log('8' != 8);	//false

console.log('8' === 8);	//false
console.log('8' !== 8);	//true
```

