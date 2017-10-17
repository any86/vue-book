### 数组

#### 错误示例

```
<p>{{map.a}</p>
<p>{{map.b}</p>
<button @click="changeMap"></button>    
```

```
// 错误示例
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







### 对象

```

```





### 



