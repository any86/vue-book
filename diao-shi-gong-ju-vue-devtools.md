### 一个神奇的调试工具

在正式开始vue课程之前, 先给大家介绍一个开发帮手vue-devtools, 有了他在调试过程中可以省去打**console.log**, 因为他会自动把我们在data上定义的数据动态的显示出来\(数据变, 他也变\).

### ![](/assets/vue-devtools.png)

### 安装

1. 首先需要大家安装nodejs
2. 下载vue-devtools [https://github.com/vuejs/vue-devtools/archive/master.zip](https://github.com/vuejs/vue-devtools/archive/master.zip), 并解压, 不要解压到桌面.
3. 解压后, 从命令行进入该文件夹.
4. 运行cnpm i, 等待安装.
5. 等待完成后, 运行 npm run build, 等待编译.
6. 编译完成后, 打开谷歌浏览器的"扩展程序"菜单.
7. 勾选打开"开发者模式".
8. 点击"加载已解压的扩展程序", 选择**shells/chrome**目录

   官方地址: [https://github.com/vuejs/vue-devtools](https://github.com/vuejs/vue-devtools)

### 测验

运行一下代码, 并用vue-devtools观察数据变化

```js
var app = new Vue({
    el: '#app', // 绑定id为app的元素, 只操作app内的标签
    data: {
        text: 'hello world'
    } // 自定义变量, 都放在data对象下面
});

setInterval(function(){
    app.text = 'hello china!' + Math.random().toString().substr(2,6);
}, 1000);
```

**注意**app.text就是data上的text, vue实例化后会自动在实例\(app\)上代理data上的数据.

### 



