### 目的

本章的目的就是让你学完这一章可以独立完成一套支持'增删改查的'表单

### 免不了俗套, 我们也从hello world开始

我们总共要做**2**步

#### 第一步

建立一个html, 在script标签中引入vue.js

```
<!DOCTYPE html>
<html>
<head>
    <script src="https://vuejs.org/js/vue.min.js"></script>
</head>
<body>
    <div id="app">
        <p v-on:click="xxx">{{text}}</p>
    </div>
</body>
</html>
```

#### 第二步

实例化vue

```
new Vue({
    el: '#app', // 绑定id为app的元素, 只操作app内的标签
    data: {
        text: 'hello world'
    }, // 自定义变量, 都放在data对象下面

    methods: {
        xxx: function(){
            this.text = 'hello china'
        }
    }
});
```

这样我们就把我们的**变量**text绑定到了p的内容中\(相当于innerText\), 当变量text变化的时候, p标签的内容会自动变化.\(稍后讲methods会展示\)

注意: 这里data中定义的变量, 在methods中调用的时候需要加'**this.',  **而模板中不需要.

### v-text

除了文本插值，我们还可以采用这样的方式绑定 DOM 元素属性：

```
<div id="app">
    <p v-text="text"></p>
</div>
```

这和上面的代码是等价的, v-text的值会被插入到标签p\(任何标签\)内部.

请记住v-text在vue中叫做指令, 指令均已"v-"开头. 当然现在可以不用着急记住v-text, 记住vue中有一个概念叫指令即可, 稍后我们会详细讲解什么是指令, 以及自己编写指令.







