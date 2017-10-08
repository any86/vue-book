### 一个神奇的调试工具

在开始vue课程之前, 先给大家介绍一个开发帮手vue-devtools, 有了他在调试过程中可以省去打**console.log**, 因为他会自动把我们在data上定义的数据动态的显示出来\(数据变, 他也变\).

![](/assets/vue-devtools.png)

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

### 安装



