### 行内快的幽灵空白问题

产生原因：行内快元素与文本的基线对齐，而文本的基线与文本最底端之间是有一定距离的

解决方案：

1. 给行内块设置`vertical`，值不为`baseline`即可，设置为`middle`、`bottom`、`top`均可
2. 若父元素中只有一张图片，给图片设置为`display: block`
3. 给父元素设置`font-size: 0`，若还有其他文本，单独设置`font-size`