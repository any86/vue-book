### 陷阱

这里说的陷阱其实是在操作数据的时候一个和我们常识不一样的地方,  这里主要涉及2中数据类型的操作: Array/Object. 下面通过例子让大家理解并规避陷阱.

### Vue自动根据数据更新dom原理

在看例子前我还是给大家简单介绍下vue自动更新dom的原理, 在js\(es5\)中Object对象有一个方法叫

### 数组

##### 错误示例

```
<p>{{map.b}</p>
<button @click="changeMap">改变</button>
```

```
new Vue({
    el: '#app',
    data: {
        map: {
            a: 1,
            b: 2
        }
    },

    methods: {
        this.changeMap(){
            this.map = {a:2,b: 3}
        }
    }
});
```

当我们点了changeMap一定以为页面内容会变成数字2和3, 但其实不会变,

### 对象

```

```

### 



