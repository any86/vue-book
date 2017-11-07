### 为什么叫浏览器中的Vue?

之所以起这个标题,就是想告诉他家, vue不仅可以在浏览器中通过&lt;script&gt;引入, 后续我还会带大家进入新的开发模式, 就是基于node工具下的开发, 届时我们会学习**webpack/es6/scss**等高级的用法, 让我们的代码更具管理性和复用性, 开发体验更接近客户端开发.

### 目的

本章的目的就是让你学完这一章可以独立完成一套支持'增删改查的'表单, 回忆我当初学vue的过程,边学边练效果更佳, 所以每节的最后 我都会带大家做一个小例子来帮助大家强化记忆, 每章的最后我们会做一个大的例子把之前的小例子的知识点串在一起, 比如第一章最后我们会做一个[todo-list](https://jsfiddle.net/yyx990803/4dr2fLb7/?utm_source=website&utm_medium=embed&utm_campaign=4dr2fLb7).

### hello world

免不了俗套, 我们先从hello world开始, 我们总共要做**2**步

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

```js
var vm = new Vue({
    el: '#app', // 绑定id为app的元素, 只操作app内的标签
    data: {
        text: 'hello world'
    } // 自定义变量, 都放在data对象下面
});
```

运行页面我们会看到'hello world'.

### `{{}}`

"`{{}}`"是vue模板插值的边界符, 通过他把变量插入模板中, 如上面的"`{{text}}`"会被编译变成hello world, 当然vue做的不仅仅是一个模板引擎, 更重要的是插入的**数据是响应的**.

### 数据是响应的

在谷歌浏览器的控制台输入**vm.text = 'hello china'**,** **页面内容从**'hello world'变成了'hello china'**, 惊讶吧, 只是操作了数据, vue帮我们自动改变了dom.

说明: Vue实例化的时候会自动把定义在data上的数据映射到实例上, 所以vm.text实际就是data上的text.

### 数据响应的原理

vue内部用了**Object.defineproperty\(\)**,这个api可以定义对对象进行读写操作的回调设置, 就是这样vue对data上的数据都重新定义并加了回调, 在回调中他会自动操作dom, 这样我们就直接通过数据操作dom.**Object.defineProperty**的第1个参数是要定义的对象, 第2个是要定义的键值, 第3个是对对象键值属性的设置, 比如get/set. 下面用**Object.defineProperty**写了个小例子, 大家体会下, 暂时不强求应用, 理解即可, 只为方便面试的时候能说明白数据响应的原理.

```js
// 定义回调
var obj = {};
var newValue = 100;
Object.defineProperty(obj, 'a', {
    get: function() {
        alert('读取: ' + newValue);
        return newValue
    },
    set: function(v) {
        newValue = v;
        alert('设置: ' + v);
    }
})

// 读操作
console.log(obj.a)
// 写操作
obj.a = 1;
```

### 定义数据

看上例可知, 我们要定义的变量都要写在data中,  比如定义一个text变量, 这个'text'的值可以是任意数据类型, 比如Object/Array/Number/String/Map/Set等等.

### 指令

```
<div id="app">
    <p v-text="text"></p>
</div>
```

这和上面在模板里插值是等价的, v-text的值会被插入到标签p\(任何标签\)内部. 这个v-text叫做指令, 指令均已"v-"开头,  vue中有大概13个系统指令\([查看](https://cn.vuejs.org/v2/api/#指令)\), 后面的课程我会为大家一一展开讲解,  系统指令内部都是封装好的一些dom操作, 当然我们也可以自定义指令, 后续的课程中我会教大家编写.有兴趣的同学可以提前看看这13个系统指令是什么.

### 测验

好了, 现在已经知道了如何用vue在模板中插值**, **接下来我们把上面的例子自己写一遍试试.

