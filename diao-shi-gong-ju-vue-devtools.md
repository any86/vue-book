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

还记得之前让大家安装的nodejs吧, 现在打开**命令行工具, 运行如下命令:**Clone this repo

1. 克隆[https://github.com/vuejs/vue-devtools.git](https://github.com/vuejs/vue-devtools.git)
2. 在nodejs命令行下运行cnpm i

3. 安装完成后, 运行npm run build

4. 打开谷歌浏览器的"扩展程序"菜单

5. 勾选打开"开发者模式"

6. 点击"加载已解压的扩展程序", 选择**shells/chrome**目录

官方地址: [https://github.com/vuejs/vue-devtools](https://github.com/vuejs/vue-devtools)



### 测验

粘贴上述代码, 并用vue-devtools观察数据变化

