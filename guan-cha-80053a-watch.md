### watch是什么?

一个告诉vue帮我们**监听指定字段**的通用方法:

```
new Vue({
    el: '#app',
    data: {
        text: 'hello!',
        timer: null
    },
    watch: {
        text: function(newValue, oldValue){
            // newValue是改变后的值(当前值)
            // oldValue是改变前的值
            clearTimeout(this.timer);
            this.timer = setTimeout(function(){
                $.post('a.php', {text: newValue});
            }, 200);

        }
    }
})
```

```
<input v-model="text"/>
```

上面的例子其实百度搜索的自动提示的一个雏形版本, 当我们修改input的值的时候. vue会根据watch值的变化自动发送信息到服务器.

不是有计算属性吗?

虽然计算属性在大多数情况下更合适，但有时也需要一个通用的**侦听器, **比如我们相同让数据的变化绑定一个异步操作, 或者在watch内部写一些对引入的第三方库的操作.

### 触发时机

watch是当观察的数据改变时候触发, vue初始化的时候不触发,

