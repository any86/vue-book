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

这里只简单的用input举例, 其他系统表单组件后续章节详细介绍, 但是有一点要提前说, 就是不仅仅是系统的表单组件可以通过v-model实现双向数据绑定, 自定义的组件也可以自定义v-model实现双向数据绑定.



