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



