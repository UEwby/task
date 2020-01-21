# v-if和v-for哪个优先级高？如果两个同时出现，应该怎么优化得到更好的性能？
#### v-for优先级高于v-if
#### 优化方案：
#### 1.过滤一个列表中的项目 (比如 v-for="item in datalist" v-if="item.actived")。在这种情形下，请将 datalist替换为一个计算属性 (比如 activedDatalist)，让其返回过滤后的列表。
#### 2.避免渲染本应该被隐藏的列表 (比如 v-for="item in datalist" v-if="showDatalist")。这种情形下，请将 v-if 移动至容器元素上 。
#### 3.最笨的方案，可以用v-show替代v-if，这个方案在效果是无异样，就是在性能上不好，因为多余渲染了隐藏的标签
