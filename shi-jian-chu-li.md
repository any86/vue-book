### 简写

```
<div v-on:click="fn"></div>
// 等价于
<div @:click="fn"></div>
```

v-on可以简写为@, 简单很多吧, 后面的例子中v-on都会@表示.  


### 内联js逻辑

```
<button @click="count+1">加1</button>
```

比如你现在

