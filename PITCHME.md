# 前端入门直播：CSS 布局

---

## 居中

统一使用下面的 HTML 结构来实例讲讲居中布局：

```html
<div class="parent">
  <div class="child">DEMO</div>
</div>
```

---

### 水平居中

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


