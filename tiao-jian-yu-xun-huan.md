### v-if

`<p v-if="isChinese">中文</p> // 如果isChinese == false, 那么页面上将什么都不显示`

v-if 是**惰性的**：如果在初始渲染时条件为假，则什么也不做——直到条件第一次变为真时，才会开始渲染条件块。

### v-else

和普通的if/else组合一样, 注意顺序即可, 即v-else前必须由一个v-if:

```
<p v-if="isChinese">中文</p>
<p v-else>英文</p>
// 如果isChinese == true, 那么页面显示'中文'二字, 否者显示'英文'.
```

### v-else-if

同样注意顺序即可, 必须在v-if后v-else前:

```
<p v-if="isChinese">中文</p>
<p v-else-if="isEnglish">英文</p>
<p v-else>日文</p>
```



