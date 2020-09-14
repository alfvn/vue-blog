# vue中的directive有哪些应用场景
vue中的指令用来做什么？对普通dom元素进行底层操作。

自定义指令。首先我们要知道内置指令有哪些：
- v-text
- v-html
- v-show
- v-if
- v-else-if
- v-for
- v-on
- v-bind
- v-model
- v-slot
- v-pre
- v-cloak
- v-once
共有13个内置指令。

语法：
```js
// 使用：在dom元素上加上v-开头的属性
<div v-focus></div>
// 定义：在组件的directives中或者全局定义 
directives: {
  focus： {
    inserted: function(el){
      el.focus()
    }
  }
}
Vue.directive('focus',{inserted: function(el){
  el.focus()
}})
```
面试官可能会问：
1. 用过自定义指令吗，一般用来做什么？
2. 手写实现v-for(考察源码)


--- 
参考：
- [指令](https://cn.vuejs.org/v2/api/#%E6%8C%87%E4%BB%A4)