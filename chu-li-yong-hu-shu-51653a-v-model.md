### 双向数据绑定

粗糙的讲, 双向数据绑定的意义就是可以让用户输入\(比如input/textara等\)自动关联界面的样式变化, 同时界面的变化也会让\(input/textara等的值随之变化\), 当然这个解释真的很粗糙, 只是为了让大家有个初步的认识, 更精准的认识需要我们后续课程的慢慢深入, 不要着急, 因为我们日后每天都离不开"双向数据绑定".





### 初识v-model

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

有一点要提前说, 其实不仅仅是系统的表单组件可以通过v-model实现双向数据绑定, 自定义的组件也可以自定义v-model实现双向数据绑定.



[更多例子](https://cn.vuejs.org/v2/guide/forms.html)

