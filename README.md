# iboot
木桶流图片布局插件

## Install
```html
  <script src="./iboot.js"></script>
```

## Use
### 初始化
```html
  <div class="iboot-controller clear">

  </div>
```

```css
.clear:after {
  content: '';
  display: block;
  clear: both;
  width: 100%;
}
```

```js
var iboot = new Iboot($('.iboot-controller'), {
  list: [
    {
      src: 'https://picsum.photos/600/600',
      alt: 'xxx'
    }
    ...
  ]
})
```
### Iboot参数
`Iboot(ele, config)`

#### ele
当前选中的元素
#### config
* <a href="#list">list</a> 
* <a href="#baseheight">baseHeight</a>  
* <a href="#template">template</a>  
* <a href="#afterload">afterLoad</a>  
* <a href="#beforeload">beforeLoad</a>  
* <a href="#resize">resize</a>  
* <a href="#loadmore">loadMore</a>  

#### list
图片列表
```js
[
  {
    src: '',
    alt: 'xxx'
  }
]
```
#### baseHeight
基准高度，图片会再次基础上放大或缩小，默认 `400`。

#### template
模板函数，此方法允许你在渲染的时候操作dom，以完成对列表自定义的一些操作，必须返回操作后的dom。

```js
template: function (dom) {
  dom.addClass('some')
  return dom
}
```

#### beforeLoad
加载图片前的回掉函数

#### afterLoad
加载图片后的回调函数

#### resize
此方法会对列表重新排版，用于窗口大小改变的时候。
```js
$(window).resize(function () {
  iboot.resize()
})

```

##### loadMore
加载更多图片
```js
iboot.loadMore([
  {
     src: 'xxx',
     alt: 'xxx'
  }
])
```


