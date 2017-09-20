# scrollTop

## 介绍

原生 JavaScript 实现的回到顶部库，适应 PC 和移动，兼容到 IE7+。

效果演示：[https://mqyqingfeng.github.io/ScrollToTop/](https://mqyqingfeng.github.io/ScrollToTop/)

## 兼容性

移动和 PC ，其中 PC 端支持 IE7+ 

## 依赖

原生 JavaScript 实现，无依赖。

## 下载

```js
git clone git@github.com:mqyqingfeng/ScrollToTop.git
```

## 使用

```html
<script src="path/ScrollToTop.js"></script>
```

或者

```js
import ScrollToTop from 'path/ScrollToTop.js'
```

## 示例

```html
<span id="toTop" class="toTop"></span>
```

```css
#toTop {
    position: fixed; right: 20px; bottom: 20px; margin-bottom: 20px; cursor: pointer; width: 0; height: 0; border-top: 30px solid transparent; border-bottom: 60px solid #3498db; border-left: 30px solid transparent; border-right: 30px solid transparent; 
}
```

```js
var toTop = new ScrollToTop("#top");
```

你也可以传入参数：

```js
var toTop = new ScrollToTop("#top", {
    // 滚动条向下滑动多少时，出现回到顶部按钮
    showWhen: 100,
    // 回到顶部的速度。
    speed: 100,
    // 元素淡入和淡出的速度
    fadeSpeed: 10
});
```

注意：当要兼容 IE7 的时候，不能传入选择符字符串，直接传入元素：

```js
var topElement = document.getElementById("toTop");
var toTop = new ScrollToTop(topElement)
```

## API

### 初始化

```js
var toTop = new ScrollToTop("selector", options);
```

### options

**1.showWhen**

默认值为 100，表示滚动条向下滑动 100px 时，出现回到顶部按钮

**2.speed**

回到顶部的速度。默认值为 100，数值越大，速度越快。

100 表示浏览器每次重绘，scrollTop 就减去 100px。

**3.fadeSpeed**

元素淡入和淡出的速度。默认值为 10，数值越大，速度越快。

10 表示浏览器每次重绘，元素透明度以 10% 递增或者递减。

### backing

当回到顶部时，按钮元素会添加一个名为 backing 的类，当按钮元素隐藏时，该类会被删除。

可以使用此类名实现正在回到顶部时的效果。
