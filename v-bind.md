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

### v-bind的简写

"**v-bind**"可简写为"**:**" , 比如

```vue
<p :align="'center'"></p>
// 等同于: <p v-bind:align="'center'"></p>
```

### Class 与 Style 绑定

这里对于class和style的绑定比较特殊, 所以单独拿出进行讲解.

1. **v-bind:class**后可赋值**对象\(Object\)**, 对象的键为class名, 值为Boolean, 为true对应的class才生效,  比如:

   ```
   new Vue({
       el: '#app',
       data:{
           hasButton: true
       }
   });
   <p v-bind:class="{btn: hasButton, 'btn-primary': hasButton, 'btn-disabled': !hasButton}"></p>
   // <p class="btn btn-primary"></p>
   ```

   **v-bind:class**后还可赋值**数组\(Array\), **数组的值为class名, 比如:

   ```
   <p v-bind:class="['btn', 'btn-primary', 'btn-disabled']"></p>
   // <p class="btn btn-primary"></p>
   ```

 

