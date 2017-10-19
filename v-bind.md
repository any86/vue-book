### 设置\(绑定\)元素属性

在**起步**中我们学习了第一个系统指令v-text, 在vue当中其实还有很多其他系统指令, 比如我们要给**input**标签设置value属性, 我们可以这么做的:

```
new Vue({
    el: '#app',
    data:{
        value: 'center'
    }
});

<p :align="value"> // <p align="center">
```

### v-bind的简写

"**v-bind**"可简写为"**:**" , 比如上面的例子:

```vue
<p :align="value"></p>
// 等同于: <p v-bind:align="value"></p>
```

### 绑定Class 与 Style 

这里对于class和style的绑定比较特殊, 所以单独拿出进行讲解.

#### v-bind:class="{}"

对象的键为class名, 值为Boolean, 为true对应的class才生效,  比如:

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

#### **v-bind:class="\[\]"**

** **数组的值为class名, 比如:

```
<p v-bind:class="['btn', 'btn-primary', 'btn-disabled']"></p>
// <p class="btn btn-primary"></p>
```

####  v-bind:style="{}"

对象语法十分直观——看着非常像 CSS，但其实是一个 JavaScript 对象。CSS 属性名可以用驼峰式 \(camelCase\) 或短横线分隔 \(kebab-case，记得用单引号括起来\) 来命名：

```
new Vue({
    el: '#app',
    data:{
        activeColor: 'red',
        fontSize: 30
    }
});

<p v-bind:style="{ color: activeColor, fontSize: fontSize + 'px' }"></p>
```

**注意: **当 v-bind:style 使用需要添加浏览器引擎前缀的 CSS 属性时，如 transform，Vue.js 会自动侦测并添加相应的前缀。

### 测验

用:style和:class分别做一个红色背景高度宽度为100px的div

