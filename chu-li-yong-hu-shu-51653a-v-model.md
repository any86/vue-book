### 认识v-model

```
new Vue({
    el: '#app',
    data:{
        value: 123
    }
});

<div id="app">
  <p>{{value}}</p>
  <input v-model="value" />
</div>
```

```
这里只简单的用input举例, 其他系统表单组件后续章节详细介绍.
```



