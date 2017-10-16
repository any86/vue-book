### v-on指令

```
<div v-on:click="fn"></div>
```

v-on后加':'加事件名来给元素绑定事件, 这里的'click'可以是任何js原生支持的事件, '='后面跟着对应的方法名.

### 定义方法

vue中所有的方法都定义在methods下,

```
new Vue({
    el: '#app',
    data: {
        count: 0
    },
    methods: {
        fn: function(){
            
        }
    }
});
```

### 简写

```
<div v-on:click="fn"></div>
// 等价于
<div @:click="fn"></div>
```

v-on可以简写为@, 简单很多吧, 后面的例子中v-on都会@表示.

### 内联js逻辑

```
new Vue({
    el: '#app',
    data: {
        count: 0
    }
});
```

```
<button @click="count+1">加1</button>
```

当一些**逻辑比较简单**的时候, 我们可以不再methods中定义方法, 而是在模板的事件绑定中直接在'='后写上逻辑.

### $event

代表绑定事件元素的event对象.

注意这只是原生html标签是上$event才表示event, 如果是自定义组件是不同的.

