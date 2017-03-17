### 准备阶段

* 首先需要几张图片	
<img src="http://img.ivsky.com/img/tupian/201007/26/xinxinanjiaowaifengjing-007.jpg" width="200" height="120px">
<img src="http://img05.tooopen.com/images/20151024/tooopen_sy_146160061542.jpg" width="200" height="120px">
<img src="http://www.anhuiyubo.com/a/img/e/f/e/3/f/9/37251.jpg" width="200" height="120px">
<img src="http://pic.qiantucdn.com/58pic/17/76/92/29358PICxSf_1024.jpg" width="200" height="120px">
<img src="http://image.tuku.china.com/tuku.travel.china.com/travel//pic/2009-01-04/43a086c5-a2d7-4f10-95b2-1c6f8dcca995.jpg" width="200" height="120px">

### 将图片置于页面中


```html
<div class="contains">
    <div class="carousel" id="carousel">
        <div class="ca-item">
            <img src="http://img.ivsky.com/img/tupian/201007/26/xinxinanjiaowaifengjing-007.jpg" alt="">
        </div>
        <div class="ca-item">
            <img src="http://img05.tooopen.com/images/20151024/tooopen_sy_146160061542.jpg" alt="">
        </div>
        <div class="ca-item">
            <img src="http://www.anhuiyubo.com/a/img/e/f/e/3/f/9/37251.jpg" alt="">
        </div>
        <div class="ca-item">
            <img src="http://pic.qiantucdn.com/58pic/17/76/92/29358PICxSf_1024.jpg" alt="">
        </div>
        <div class="ca-item">
            <img src="http://image.tuku.china.com/tuku.travel.china.com/travel//pic/2009-01-04/43a086c5-a2d7-4f10-95b2-1c6f8dcca995.jpg" alt="">
        </div>
    </div>
</div>
```

### 添加样式

* 让图片居中并隐藏不需要出现的那部分

```css
.contains {
    width: 600px;
    margin-left: auto;
    margin-right: auto;
    height: 350px;
    overflow: hidden;
    position: relative;
}
```

* 让图片在同一高度平铺

```css
.carousel {
    width: 3000px;
    position: absolute;
    transform: all 1000ms ease;
}
```

* 限制图片宽高

```css
.contains .carousel .ca-item {
    float: left;
    width: 600px;
    height: 350px;
}
.contains .carousel .ca-item img {
    width: 100%;
    height: 100%;
}
```

### 添加脚本，实现轮播

> 设置每5000ms就往左移动600个像素，也就是一个图片的宽度

```javascript
var i = 0;

function carouselEvent() {
    var carousel = document.getElementById('carousel');
    setInterval(function() {
        console.log(i++);
        if (i > 4) i = 0;
        carousel.style.left = i * -600 + 'px';
    }, 5000)

}
carouselEvent();
```