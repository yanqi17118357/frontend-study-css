## 前端css学习笔记


### 选择器优先级
格式: (a, b, c)
a: ID选择器个数
b: 类、伪类、属性选择器个数
c: 标签、伪元素选择器个数

!important > 行内样式 > ID选择器 > 类、伪类、属性选择器 > 标签、伪元素选择器 > 通配符选择器 > 继承 > 默认


### 字体相关
字体复合写法:
```css
/* 规则: 
1. 使用空格隔开
2. font-size(倒数第二位), font-family(最后一位)必须都写上 */
font: font-style font-variant font-weight font-size/line-height font-family;
```
