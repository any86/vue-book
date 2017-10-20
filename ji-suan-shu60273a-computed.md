### 为什么要用计算属性

之前我们在讲解`v-bind`时候说data上定义的变量都可以在模板中直接调用, 但是当表达式比较复杂的时候就不建议直接写在模板中了, 而是放在计算属性中, 代码更优雅.

```
new Vue({
    el: '#app',
    data: {
        message: 'Hello World'
    },
    computed: {
        reverseMessage: function(){
            return this.message.split('').reverse().join('');
        }
    }

})
```

```
<p>表达式返回: {{message.split('').reverse().join('')}}</p>
<p>计算属性返回: {{reverseMessage}}</p>
```

每当**this.message**发生变化, reverseMessage会自动重新计算新值, 绑定计算属性的元素也会响应变化.

### 缓存

当参与计算的属性没有发生变化, 那么计算属性是自动缓存的, 无论是在模板还是js中调用计算属性他都不会重新计算, 这相比绑定表达式多次调用会被多次计算相比性能更优. 试想想如果我们计算属性内部的逻辑是处理1000条产品信息, 建议大家实际开发中优先使用计算属性.

