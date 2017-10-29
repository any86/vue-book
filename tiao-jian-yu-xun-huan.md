### v-if

`<p v-if="isChinese">中文</p> // 如果isChinese == false, 那么页面上将什么都不显示`

v-if 是**惰性的**：如果在初始渲染时条件为假，则什么也不做——直到条件第一次变为真时，才会开始渲染条件块。

### v-else

和普通的if/else组合一样, 注意顺序即可, 即v-else前必须由一个v-if:

```
<p v-if="isChinese">中文</p>
<p v-else>英文</p>
// 如果isChinese == true, 那么页面显示'中文'二字, 否者显示'英文'.
```

### v-else-if

同样注意顺序即可, 必须在v-if后v-else前:

```
<p v-if="isChinese">中文</p>
<p v-else-if="isEnglish">英文</p>
<p v-else>日文</p>
```

### :key

当遇到v-if/v-else的时候, 如果2个所在html标签相同, 决策元素是同时渲染2个相同的html元素, 还是复用, 此特性不常用,  可使用的时候翻阅[官方文档](https://cn.vuejs.org/v2/guide/conditional.html#用-key-管理可复用的元素)说明. 而且:key在vdom渲染逻辑中也是一种唯一标记, 可理解为元素/组件的唯一id.

特别需要记住, 在做**动画**的时候和**循环**元素的时候都需要给元素标记:key, 不然会提示错误.

### v-show

和v-if一样可以控制元素的显示, 不同的是v-show是通过控制元素是否有display: none; 来控制显藏. 而v-if是真通过是否有这个元素来控制.

特别要注意v-show不支持和v-else/v-else-if配合使用. 如果要控制2个元素的显示隐藏, 只能分别给2个元素添加v-show.

```
<p v-show="isChinese">中文</p>
<p v-show="!isChinese">英文</p>
```

### &lt;template&gt;

为了更灵活的使用v-if, 我们可以使用&lt;template&gt;进行对多个元素的统一管理:

```
<template v-if="isChinese">
    <p>简体中文</p>
    <p>繁体中文</p>
</template>
<p v-else>其他语种</p>

// 如果isChinese == true
// <p>简体中文</p>
// <p>繁体中文</p>
// 否则只显示 <p>其他语种</p>
```

### 测验

把上面的例子都练一遍.



