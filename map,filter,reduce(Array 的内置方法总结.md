# map, filter, reduce（Array 的内置方法）总结

  map 作用是生成一个新数组，遍历原数组，将每个元素拿出来做一些变换然后放入到新的数组中  

```js
[1, 2, 3].map(v => v + 1) // -> [2, 3, 4]
```

  filter 的作用也是生成一个新数组，在遍历数组的时候将返回值为 true 的元素放入新数组，我们可以利用这个函数删除一些不需要的元素
  ```js
let array = [1, 2, 4, 6]
let newArray = array.filter(item => item !== 6)
console.log(newArray) // [1, 2, 4]
  ```

  reduce 可以将数组中的元素通过回调函数最终转换为一个值。

    如果我们想实现一个功能将函数里的元素全部相加得到一个值，可能会这样写代码

  ```js
  const arr = [1, 2, 3]
let total = 0
for (let i = 0; i < arr.length; i++) {
  total += arr[i]
}
console.log(total) //6 
  ```
  但是如果我们使用 reduce 的话就可以将遍历部分的代码优化为一行代码

  ```js
const arr = [1, 2, 3]
const sum = arr.reduce((acc, current) => acc + current, 0)
console.log(sum)
  ```