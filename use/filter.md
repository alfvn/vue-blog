# vue 中的filter有哪些应用场景
根据官方文档，过滤器被划分在可复用性&组合下面，第一句就说了，可被用于一些常见的文本格式化。语法是：
```js
// 1.在双花括号插值和v-bind表达式中使用
<div>{{message || format}}</div>
// 2.在组件内的 filters中定义，或者在全局 Vue.filter('format',function(value){})
filters: {
  format: function(value){}
}
Vue.filter('format',function(value){})
```

应用场景：
1. 文本格式化
  - 首字符大写
```js
Vue.filter('format', function(value){
  if(!value) return;
  value = value.toString()
  return value.charAt(0).toUpperCase() + value.slice(1)
})
```
面试官可能会这样问：在vue开发中需要对文本做一些格式化处理，比如后端返回给你的一些状态，需要做一些map，变成前端展示的文案。你一般会采用什么方案？
可能刚开始看到这个的时候，会觉得，直接在接收数据的回调函数中处理不就行了么，事实上我们可能也经常是这样做的。filter可能在可复用性上确实存在一些优势

---
参考：
- [过滤器](https://cn.vuejs.org/v2/guide/filters.html)