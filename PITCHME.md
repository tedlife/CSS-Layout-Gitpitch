# 前端入门：CSS 布局

---

## CSS Reset

什么是 CSS Reset？为什么要使用 CSS Reset？

---

### CSS Reset 简介

* HTML 标签在浏览器中都有默认的样式，不同的浏览器的默认样式之间存在差别。例如 ul 默认带有缩进样式，在 IE 下，它的缩进是由 margin 实现的，而在 Firefox 下却是由 padding 实现的。
* 同时，有时候浏览器添加的默认样式，我们并不需要，会影响我们的开发效率，比如说各种元素默认的 padding 和 margin。大部分是不需要的。

这个时候我们就需要用 CSS Reset 来修正。

---

### CSS Reset 如何写

这里提供几个常用的 CSS reset。

---

最流行的是使用 [normalize.css](https://necolas.github.io/normalize.css/) 以及 [HTML5-Reset](https://github.com/murtaugh/HTML5-Reset)。

优点是：比较全面

缺点是：代码有点多，不适合小练习，小项目

---

还有一种非常简洁的写法，适合我们平时的小练习或小项目：

```css
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
```

---

或者这样写，也行，更方便后面修改：

```css
html {
  box-sizing: border-box;
}

*, *:before, *:after {
  box-sizing: inherit;
}
```

---

## 居中布局

统一使用下面的 HTML 结构来实例讲讲居中布局：

```html
<div class="parent">
  <div class="child">DEMO</div>
</div>
```

代码实例请查看：[CSS 居中布局](http://codepen.io/ista/pen/XRaGqe)

---

### 水平居中

---

#### 方法一：inline-block + text-align

```css
.child {
  display: inline-block;
}

.parent {
  text-align: center;
}
```

优点：兼容性好，可以兼容到 IE6，7

缺点：子元素会继承 center，需要额外设置

---

#### 方法二：table + margin

```css
.child {
  display: table;
  margin: 0 auto;
}
```

优点：只需对 child 设置就好了

---

#### 方法三：absolute + transform

```css
.parent {
  position: relative;
}

.child {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
}
```

优点：不会对其他元素产生影响

缺点：transform 是 css3 的属性，对旧版浏览器不兼容，包括 IE8

---

#### 方法四：flex + justify-content

```css
.parent {
  display: flex;
  justify-content: center;
}

.child {
	/*margin: 0 auto; */
}
```

优点：flex 是未来，只需要设置父元素即可

缺点：flex 兼容性

---

### 垂直居中

---

#### 方法一：table-cell + vertical-align

```css
.parent {
  display: table-cell;
  vertical-align: middle;
}
```

优点：兼容到 IE8 及以上，同时不管父元素和子元素高度大小

---

#### 方法二：absolute + transform

```css
.parent {
  position: relative;
}
.child {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
}
```

优点：不会对其他元素产生影响

缺点：transform 是 css3 的属性，对旧版浏览器不兼容，包括 IE8

---

#### 方法三：flex + align-items

```css
.parent {
  display: flex;
  align-items: center;
}
```

优点：flex 是未来，只需要设置父元素即可

缺点：兼容性问题

---

### 水平与垂直居中

同时实现水平与垂直居中，可以把上面的方法组合起来使用，作为课后练习小作业，使用在线代码编辑器 [codepen](http://codepen.io/)。

---

## 多列布局

多列布局可以分为：定宽与自适应，不定宽与自适应，等分，等高几个情况，有兴趣的可以看看我写的实例演示：[CSS 多列布局](https://codepen.io/ista/pen/WjXjXJ)

---

## 全屏多列布局

全屏多列布局可以使用两种方式实现：Position 和 Flex，有兴趣可以看看我洗的实例演示：[CSS 全屏多列布局 - Position](https://codepen.io/ista/pen/WjXEbQ) 和 [CSS 全屏多列布局 - Flex](https://codepen.io/ista/pen/oWoewJ)

---

# 前端工具

这次介绍前端工作中必不可少的切图流程的工具。切图，取色，量各种大小与间距等等，都可以通过这些工具一站解决。

---

## 国外的服务

* [avocode](https://avocode.com/)，付费的，可以试用，每月至少6.75 美元，但是应该是我目前用过的最强大的一款。
* [zeplin](https://zeplin.io/)，有免费 plan，但仅限 1 个项目
* [Sympli](https://sympli.io/)，也是可以免费 1 个项目
* [Sketch Measure](http://utom.design/measure/)，非常强大的一款 Sketch 插件，完全免费。

前三款都是支持 Sketch，Photoshop 插件直接上传设计稿。

---

## 国内类似的服务

* [标你妹](http://www.biaonimeia.com/)，免费
* [蓝湖](https://www.lanhuapp.com/)，免费
* [Cutterman](http://www.cutterman.cn/zh/cutterman) 和 [Parker](http://www.cutterman.cn/zh/parker)，同一个人开发的 Photoshop 插件。CuttermAn 是用来切图的且免费。Parker 是用来标注的且付费的。
* [PxCook](http://www.fancynode.com.cn/pxcook)，依赖 Adobe AIR 的程序，免费跨平台。

---

# 前端前沿

最新最前沿的前端技术发展，可能会让你感兴趣的东西。

---

* 聊天机器人，语音搜索为代表的人工智能在前端的应用，还有更多：[10 Machine Learning Examples in JavaScript](http://tutorialzine.com/2017/04/10-machine-learning-examples-in-javascript/)
* WEBVR，AR 为代表的虚拟现实在前端的应用，比如[Argon.js](https://www.argonjs.io/) 和 [awe.js](https://github.com/awe-media/awe.js)
* WebGL 为代表的 Web 3D 绘图
* CSS GRID，CSS Flex 为代表的新一代网页布局方法
* SVG 与 SVG 动画的应用
* Node.js, Vue.js，Angular.js，React.js 为代表的前端框架，gulp，webpack 为代表的自动化构建工具

---

# 其它

* 每个人注册一个 [Github](https://github.com/) 账号
* 每个人注册一个[知乎](https://www.zhihu.com/)账号，每个月一篇学习总结，优秀还有机会获得几百元稿费。
* 了解下 Markdown
* 了解下 CSS 中 BFC 的概念

注册完，把 Github 用户名和知乎主页链接发给我。

另外，把你目前完成的进度截图发给我。

