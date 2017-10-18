### 变量在操作前必须在data上定义

还记得之前咱们说过的vue的核心原理**Object.defineproperty\(\)**吗? 第二个参数是键值, 所以如果我们想要vue识别我们操作数据的动作, 那么就必须提前在data上定义变量, 让他提前帮我们做好数据的响应准备.

**错误:**

```
<p>{{num}}</p>
<button @click="setNum">确定</button>
```

```
new Vue({
    el: '#app',
    data: {},
    methods: {
        setNum(){
            this.num = 1;
        }
    }
});
```

![](/assets/QQ20171018-083902.png)

不要以为点击了按钮页面就会显示数字1哦, 因为没有在data中定义num, 所以vue并没有对num进行监听, 所以也就没有dom的变化, **尽管你的数据已经改变了**.

**正确:**

```
new Vue({
    el: '#app',
    data: {num: 0},
    methods: {
        setNum(){
            this.num = 1;
        }
    }
});
```

现在点击按钮后, 页面显示数字2.

### 陷阱

这里说的陷阱其实是在操作数据的时候一个和我们常识不一样的地方,  这里主要涉及2种数据类型的操作: Array/Object. 下面通过例子让大家理解并规避陷阱.

### 

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



