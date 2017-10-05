### 免不了习俗, 我们也从hello world开始

我们总共要做5步

#### 第一步

建立一个html, 在script标签中引入vue.js

```
<script src="vue.js"></script>
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



