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

**v-for**也可以循环整数。在这种情况下，它将重复多次模板\(平时做测试会用的多些\).

```
<div>
  <span v-for="n in 10">{{ n }} </span>
</div>
```

### :key

默认每个循环的元素都相当于隐式的加了:key="$index", $index是循环的索引, 他的意义是当我们循环一个数组, 然后打乱数组顺序, 默认vue不会重新渲染每个节点, 而是重新给每个节点赋值和赋属性值, 虽然性能非常好, 但是一些情况下比较失控.

比如之前input的例子, 还有当对循环的每一项都加**位移动画**的时候, 如果没有独立的key, 那么你会发现动画会非预期的变化\(后续讲动画的时候会给大家演示\).

所以强烈建议给循环的每个元素都要key, 除非你十分需要这个部分复用带来的性能, 一般开发中很少遇到非要复用的情况.

**注意: **vue2.20版本后要求 **:key**在v-for循环时必填.

```
<span v-for="n in 10" :key="n">{{ n }} </span>
```

### 配合v-if

某些场合我们需要过滤功能:

```
<div v-if="n < 3" v-for="n in 5">{{n}}</div>
<div v-else>{{100 + n}}</div>
//<div>1</div>
//<div>2</div>
//<div>103</div>
//<div>104</div>
//<div>105</div>
```

**注意**循环数字, 循环的第一项是1不是0.

### 测验

结合input框的"v-bind:value"做一个带筛选功能的表格, 简单实现即可, 样式/表格里面的内容随意发挥.

