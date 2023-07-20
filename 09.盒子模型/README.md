## 盒子模型
---

### 1.盒子模型的组成
- 内容(content)
- 内边距(padding)
- 边框(border)
- 外边距(margin)

### 2.内容区
注意设置宽高后就固定了，即使缩放浏览器也不会跟着改变

```css
div{
    /* 最小宽度是100px，视口宽度大于100px会撑满视口，小于100px就固定为100px */
    min-width: 100px;
    /* 由于块级元素高度属性是跟着内容的高度变化的，当内容高度小于100px是固定为100px，否则由内容的高度所决定 */
    min-height: 100px;
}
```

```css
div{
    /* 最大宽度是100px，视口宽度小于100px会撑满视口，大于100px就固定为100px */
    max-width: 100px;
    /* 由于块级元素高度属性是跟着内容的高度变化的，当内容高度大于100px是固定为100px，否则由内容的高度所决定 */
    max-height: 100px;
}
```

### 3.关于默认宽度
所谓的默认宽度，指的是不设置`width`属性时，元素的宽度。
总宽度 = 父的`content` - 自身的左右`margin`
内容区的宽度 = 父的`content` - 自身的左右`padding` - 自身的左右`border`

### 4.盒子的内边距
行内元素的上下内边距不能完美设置，会有遮挡，块级和行内块元素的没有问题
一些常用的内边距属性：
```css
div {
    padding-top: 10px;
    padding-right: 20px;
    padding-bottom: 30px;
    padding-left: 40px;
    padding: 10px 20px 30px 40px; // 上右下左
    padding: 10px 20px 30px; // 上左右下
    padding: 10px 20px; // 上下 左右
    padding: 10px; // 上下左右
}
```

### 5.盒子的边框
20个边框属性：
```css
div {
    border-top-width: 10px;
    border-right-width: 20px;
    border-bottom-width: 30px;
    border-left-width: 40px;

    border-top-style: solid;
    border-right-style: dashed;
    border-bottom-style: dotted;
    border-left-style: double;

    border-top-color: red;
    border-right-color: red;
    border-bottom-color: red;
    border-left-color: red;

    border-top: 10px solid red;
    border-right: 10px solid red;
    border-bottom: 10px solid red;
    border-left: 10px solid red;

    border-color: red;
    border-width: 10px;
    border-style: solid;
    border: 10px solid red;
}
```

### 6.盒子的外边距
与内边距一样，外边距也有一些常用的属性：
```css
div {
    margin-top: 10px;
    margin-right: 20px;
    margin-bottom: 30px;
    margin-left: 40px;

    margin: 10px 20px 30px 40px; // 上右下左
    margin: 10px 20px 30px; // 上左右下
    margin: 10px 20px; // 上下 左右
    margin: 10px; // 上下左右
}
```

### 7.margin的注意事项
1. 子元素的margin是参考父元素的content计算的
2. 上margin、左margin影响自己的位置，下margin、右margin影响兄弟元素的位置
3. 行内元素左右margin可以完美设置，上下margin设置无效
4. 块级元素设置左右margin为auto，该块级元素会居中显示
5. margin的值可以为负数

### 8.margin塌陷问题
什么是margin塌陷？
第一个子元素的上margin会作用在父元素上，最后一个子元素的下margin会作用在父元素上

如何解决margin塌陷？
1. 给父元素添加`overflow: hidden;`
2. 给父元素添加`padding: 1px;`
3. 给父元素添加`border: 1px solid transparent;`

### 9.margin合并问题
什么是margin合并？
上面兄弟元素的下外边距和下面兄弟的上外边距会合并，取其中一个最大的值

如何解决margin合并？
无需解决，只给一个设置上下边距就可以了
