# ES6字符

字符编码方面可以看有关 `Unicode` 值的文章
但要记住的是 `utf-8` 是大多数开发者使用的。

## ES6变化

在ES5中，如果采用 `'\u1F68'` 这样的写法来表达 `Ὠ`对应的Unicode码是 `1F68` 

```js
console.log('\u1F680')
// print Ὠ0
```

如果超出了 `FFFF` 这个大小，则只能使用 `String` 类提供的函数 `String.fromCodePoint()` 去表达 `FFFF` 以上的符号

```js
console.log(String.fromCodePoint(0x1f680))
// print 🚀
console.log(String.fromCharCode(75))
// print K
```

ES6优化了这个写法，使你尽可能的用简单的代码去表达你所要的符号
`\u{1F680}` 只要在超出 `FFFF` 的数值前加上一对大括号，即可正确表示出来

```js
console.log('\u{1F680}')
// print 🚀
```
