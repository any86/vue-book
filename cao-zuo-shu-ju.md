### 变量在操作前必须在data上定义

还记得之前咱们说过的vue的核心原理**Object.defineproperty\(\)**吗? 第二个参数是键值, 所以如果我们想要vue响应我们的数据操作, 那么就必须提前在data上定义变量, 让他提前帮我们做好数据的响应准备.

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

现在点击按钮后, 页面显示**数字1**.

### 对象\(Object\)

由于**Object.defineproperty**只能定义get/set**, **也就是说vue对于Object类型的数据是不能响应**删除/添加**操作的, 所以vue在其实例上提供了**$set**方法来对非根\(也就是非data下的第一层\)添加数据,  比如:

```
new Vue({
    el: '#app',
    data: {
        map: {
            a: 1
        }
    },
    methods: {
        addToMap(){
            this.map.b = 2; // 错误, vue是不会把数据响应到dom的
            this.$set(this.map, 'a', 2); // 正确
        }
    }
});
```

至于**删除**我的建议是结合**v-if**来禁止渲染到页面:

```
<p v-if="null === map.a">{{map.a}}</p>
<button @click="removeFromMap">删除</button>
```

```
new Vue({
    el: '#app',
    data: {
        map: {
            a: 1
        }
    },
    methods: {
        remveFromMap(){
            this.a = null;
        }
    }
});
```

### 数组

由于**Object.defineproperty**只能定义**对象\(Object\)**的get/set**,  **所以对于数组的操作Vue通过改变Array类型数据的**原型\(prototype\)**上的方法来实现数组数据的自动响应.

这些方法包括: **push**\(\) / **pop**\(\) / **shift**\(\) / **unshift**\(\) / **splice**\(\) / **sort**\(\) / **reverse**\(\)

这里有一个特别要注意的操作就是, vue不能检测到**通过索引设置值**的这个动作, 看下面的**错误**的例子: 

```
<p v-for="item in list" :key="item">{{item}}</p>
<button @click="edit">让第一个元素等于100</button>
```

```
new Vue({
    el: '#app',
    data: {
        list: [1, 2, 3]
    },

    methods: {
        edit: function(){
            this.list[0] = 100; // 错误, 不会生效
        }
    }
});
```

当我们点了按钮一定以为页面会出现数字100,2, 3, 但实际页面是不会有变化的, 就想上面解释的, vue不能检测到**通过索引设置值**的这个动作, 所以**正确**的方式是:

```
new Vue({
    el: '#app',
    data: {
        list: [1, 2, 3]
    },

    methods: {
        edit: function(){
            this.list.splice(0, 1, 100);
        }
    }
});

```

### 



