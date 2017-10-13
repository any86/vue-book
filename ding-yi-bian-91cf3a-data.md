这里只是简单先介绍下如何定义变量和方法, 稍后的课程会深入讲解.

### 定义变量/方法

```
new Vue({
    el: '#app',
    data: {
        message: 'hello'
    },
    methods: {
        say: function(){
            alert(message);
        }
    }
    
});
```

定义变量尽量不要以\_开头, 官方推荐$\__namespace\_xxx._

### 



