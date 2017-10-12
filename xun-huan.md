### 语法

```
<xxx v-for="item in items">
    <xx>{{item}}</xx>
</xxx>
```

用指令**v-for**来处理循环,  items是循环体, 循环体的数据类型可以是Array/Object/Number, item是每次循环的存储当前项的临时变量.

#### 循环数组

```
<ul id="example-1">
  <li v-for="item in items">
    {{ item.message }}
  </li>
</ul>
```

```
var example1 = new Vue({
  el: '#example-1',
  data: {
    items: [
      { message: 'Foo' },
      { message: 'Bar' }
    ]
  }
})

// 结果是:
// <ul id="example-1">
//     <li>Foo</li>
//     <li>Bar</li>
// </ul>
```

对于数组, 每次循环还可以获取数组的**索引**:

```
<ul id="example-1">
  <li v-for="(item, index) in items">
    {{ item.message }}
  </li>
</ul>
// 0
// 1
```

#### 循环对象

```
<ul id="example-2">
  <li v-for="(item, key, index) in items">
    {{ key }} : {{index}} : {{item}}
  </li>
</ul>
```

```
var example2 = new Vue({
  el: '#example-2',
  data: {
       message1: 'Foo' ,
       message2: 'Bar'
  }
});

// 结果是: 
// <ul id="example-2">
//     <li>Foo</li>
//     <li>Bar</li>
// </ul>
// 这个顺序会因浏览器不同而不同
```

这里特必要注意key, 他代表的是对象当前的键值

### 循环数字

**v-for**也可以循环整数。在这种情况下，它将重复多次模板。

```
<div>
  <span v-for="n in 10">{{ n }} </span>
</div>
```

### :key



