### 陷阱

这里说的陷阱其实是在操作数据的时候一个和我们常识不一样的地方,  这里主要涉及2中数据类型的操作: Array/Object

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

当我们点了

### 对象

```

```

### 



