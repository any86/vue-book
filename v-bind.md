### 设置\(绑定\)元素属性

在**起步**中我们学习了第一个系统指令v-text, 在vue当中其实还有很多其他系统指令, 比如我们要给**input**标签设置value属性, 我们可以这么做的:

```
new Vue({
    el: '#app',
    data:{
        value: 123
    }
});

<input :value="value"> // <input value="123">
```

### 简写

"v-bind"可简写为":" , 比如

```vue
<p :align="'center'"></p>
// 等同于: <p v-bind:align="'center'"></p>
```

### Class 与 Style 绑定

这里对于class和style的绑定比较特殊, 所以单独拿出进行讲解.



