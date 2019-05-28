# repaint && reflow

>repaint是某个DOM元素进行重绘；

>reflow是整个页面进行重排，也就是页面所有DOM元素渲染。

## 如何触发：

>style变动造成repaint和reflow。

>不涉及任何DOM元素的排版问题的变动为repaint，例如元素的color/text-align/text-decoration等等属性的变动。

>除上面所提到的DOM元素style的修改基本为reflow。例如元素的任何涉及长、宽、行高、边框、display等style的修改。

## 常见触发场景：

### 1. 触发repaint：  

    1. color的修改，如color=#ddd；  
    2. text-align的修改，如text-align=center；  
    3. a:hover也会造成重绘。  
    4. :hover引起的颜色等不导致页面回流的style变动。  
  

### 2. 触发reflow：

    width/height/border/margin/padding的修改，如width=778px；  

    动画，:hover等伪类引起的元素表现改动，display=none等造成页面回流；  

    appendChild等DOM元素操作；  

    font类style的修改；  

    background的修改，注意着字面上可能以为是重绘，但是浏览器确实回流了，经过浏览器厂家的优化，部分background的修改只触发repaint，当然IE不用考虑；  

    scroll页面，这个不可避免；  

    resize页面，桌面版本的进行浏览器大小的缩放，移动端的话，还没玩过能拖动程序，resize程序窗口大小的多窗口操作系统。  

    读取元素的属性（这个无法理解，但是技术达人是这么说的，那就把它当做定理吧）：读取元素的某些属性（offsetLeft、offsetTop、offsetHeight、offsetWidth、scrollTop/Left/Width/Height、clientTop/Left/Width/Height、getComputedStyle()、currentStyle(in IE))；  