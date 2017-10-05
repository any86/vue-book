### 免不了俗套, 我们也从hello world开始

我们总共要做**2**步

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
</body>
</html>
```

#### 第二步

实例化vue

```
new Vue({
    el: '#app',
    data: {
        text: 'hello world'
    }
});
```

除了文本插值，我们还可以采用这样的方式绑定 DOM 元素属性：

