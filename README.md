# 《HTML常用标签》

## 一、a标签的用法
a标签有两个常用属性：href/target

href属性值：<br>
1.网址：https://google.com http://google.com；<br>
2.路径：绝对路径：/a/b/c；相对路径：a/b/c；<br>
3.伪协议：JavaScript:代码（点击a标签不会产生任何反应）、mailto:邮箱、tel:手机号；<br>
4.id:a标签href=#xxx，点击后，页面会跳转到标签id=xxx的地方（锚点）；

【补充】href="空值"点击页面会刷新；href="#"点击链接会跳转到当前页面的顶部；

```HTML
<a href="http://google.com">网址</a>
<a href="/a/b/c">路径</a>
<a href="javascript:;">伪协议点击不会产生任何反应</a>
<a href="#xxx">id锚点跳转</a>
```
target属性值:_blank、_top、_parent、_self<br>

_blank:在新的空白页面打开链接

_top:在当前页面顶部打开

_parent:在当前页面上一层打开链接

_self:默认值，在自身打开

window的name在以name为xxx的窗口链接打开

iframe的name在以name为xxx的iframe框架打开链接
【补充】a的download作用是不是打开页面，而是下载页面，不是所有浏览器都支持，尤其是手机浏览器；iframe内嵌窗口，已经很少使用。
<br>
### a标签总结

1.跳转外部页面

2.跳转内部锚点

3.跳转到邮箱或电话等<br><br>

### 二、img标签的用法
1.img的作用：发出get请求，展示一张图片

2.img标签属性：alt/height/width/src

alt:图片请求失败，显示alt内容提示我们

width:设置图片的宽度

height:设置图片的高度

src:图片的路径

【补充】:不要同时设置图片的宽度与高度，这样会使图片变形，只设置宽度和高度其中一个属性，另一个属性会自动适应，达到图片不变性又可以改变（使用工具也可以）

3.事件:onload/onerror

onload：图片加载成

onerror：图片加载失败

可以使用事件监听图片是否请求成功或失败

```javascript
xxx.onload = function(){
    console.log("图片加载成功")
}；
xxx.onerror = function(){
    console.log("图片加载失败")
    //图片加载失败我们可以使用补救措施
    xxx.src="路径"
}；
```
4.响应式：max-width：100%

这段代码可以使图片自动适应兼容手机
```css
img{
max-width：100%
}
```

## 三、table标签的用法

1.相关标签：table/thead/tbody/tfoot/tr/td/th

table标签的基本格式
```html
<table>
    <tr>
        <th>111</th>
        <th>222</th>
    </tr>
    <tr>
        <th>333</th>
        <th>444</th>
    </tr>
</table>
```

每个表格有若干行（由<tr>标签定义），每行被分割为若干单元格（由<td>标签定义）。<td>标签中的内容，即数据单元格的内容（可包含文本、图片、列表、段落等。）

2.相关样式：table-layout/border-collapse/border-spacing

table-layout:outo(默认，自动表格布局)、fixed(固定表格布局)inherit(继承复元服table-layout属性值，不支持IE)
border-collapse:常用该属性合并单元格
border-spacing:单元格之间的间距