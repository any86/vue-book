### 目的

本章的目的就是让你学完这一章可以独立完成一套支持'增删改查的'表单, 回忆我当初学vue的过程,边学边练效果更佳, 所以每节的最后 我都会带大家做一个小例子来帮助大家强化记忆, 每章的最后我们会做一个大的例子把之前的小例子的知识点串在一起, 比如第一章最后我们会做一个[todo-list](https://jsfiddle.net/yyx990803/4dr2fLb7/?utm_source=website&utm_medium=embed&utm_campaign=4dr2fLb7).

### hello world

免不了俗套, 我们也从hello world开始, 我们总共要做**2**步

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
        <p>{{text}}</p>
    </div>
</html>
```

#### 第二步

实例化vue

```
var vm = new Vue({
    el: '#app', // 绑定id为app的元素, 只操作app内的标签
    data: {
        text: 'hello world'
    } // 自定义变量, 都放在data对象下面
});
```

运行页面我们会看到'hello world'.

### `{{}}`

"`{{}}`"是vue模板插值的编辑符, 通过他把变量插入模板中, 如上面的"`{{text}}`"会被编译变成hello world, 当然vue做的不仅仅是一个模板引擎, 更重要的是插入的**数据是响应的**.

### 数据是响应的

我们尝试在谷歌浏览器的控制台输入vm.text = 'hello china', 浏览器显示的内容从'hello world'变成了'hello china', 惊讶吧, 我们并没有操作dom哦, 只是操作了数据, 然后vue帮我们自动改变了dom. 这里在控制台去改数据只是我们还没有学习输入绑定事件, 当我学会绑定事件后, 我们就可以在自定义方法中痛快的操作数据了.





### 定义数据

看上例可知, 我们要定义的变量都要写在data中,  比如定义一个text变量, 这个'text'的值可以是任意数据类型, 比如Object/Array/Number/String/Map/Set等等

### 定义方法

所有的方法定义都在methods这个对象中定义, 如上例的xxx方法.

### js中调用数据

在方法中调用数据, 我们定义的变量会挂在vue实例上, 比如'text'可通过this.text访问.

### 模本中调用数据

模板中不需要加this, 可以直接用text表示, vue会自动解析.

### js中调用方法

和data的调用方式一样, 方法也存在于vue实例上, 在js中用'this.xxx\(\)'来调用 .

### 模板中调用方法

在模板中用v-on="方法名"来调用. 如上例v-on="xxx".

### 指令

v-on在vue中叫做系统指令, 指令都是以v-开头, 他代表系统封装的一系列内部dom操作, 指令是vue中非常重要的概念, 这样指令还有很多, 比如上例除了文本插值，我们还可以采用这样的方式绑定 DOM 元素属性：

```
<div id="app">
    <p v-text="text"></p>
</div>
```

这和上面的代码是等价的, v-text的值会被插入到标签p\(任何标签\)内部.

好了我们这节学了2个指令: v-text/v-model, 请大家牢记, 因为这是vue开发中最常用的2个指令, 系统指令有13个\([查看](https://cn.vuejs.org/v2/api/#指令)\), 有兴趣的同学可以先睹为快.'

### 组件

vue最大的亮点不是模板功能, 而是组件, 让我们把一系列的js/html/css分装成一个html标签 , 展示一下封装好的组件代码和[运行效果](https://cn.vuejs.org/v2/examples/modal.html).

### 测验

现在已经知道了vue中最核心的3个概念, **数据/方法/指令,**好了把上面的例子自己写一遍试试.

