---
title: css媒体查询
date: 2018-09-12 15:39:42
tags:
  - css
  - media query
---
### 这里只列举一些常用的值，详情可以看[这里](https://www.w3schools.com/cssref/css3_pr_mediaquery.asp)
# 语法
语法概览
```
  @media not|only mediatype and (media feature and|or|not mediafeature){
    ...css-code;
  }
```
示例
```html
<!-- link元素中的css媒体查询 -->
<link rel="stylesheet" media="(max-width: 800px)" href="example.css" />

<!-- 样式表中的css媒体查询 -->
<style>
@media (max-width: 600px){
  .hd{
    display: none;
  }
}
</style>
```

# Javascript中判断媒体查询
```javascript
  const mq = window.matchMedia('(min-width: 500px)');
```

# 逻辑操作符
* and
```css
  @media tv and (min-width: 700px) and (orientation: landscape){
    /* ... */
  }
```
* or
```css
  @media (min-width: 700px), handheld and (orientation: landscape){
    /* ... */
  }
```
* not
```css
  /*
   * not应用于整个媒体查询语句
   */
   /* 等价于 not (all and (monochrome)) */
  @media not all and (monochrome) {
    /* ... */
  }
  /* 等价于 (not (screen and (color))), print and (color) */
  @media not screen and (color), print and (color){
    /* ... */
  }
  
```
* only：主要用于防止老旧的浏览器不支持带媒体属性的查询而应用给给定的样式
```html
  <link rel="stylesheet" media="only screen and (color)" href="example.css" />
```

# 媒体特征

## aspect-radio(宽高比)
* ### 是否接受min/max前缀: 是
* ### 描述了输出设备目标显示区域的宽高比。该值包含两个以“/”分隔的正整数。代表了水平像素数（第一个值）与垂直像素数（第二个值）的比例。
```css
@media screen and (min-aspect-ratio: 1/1){
  /* ... */
}
```

## device-aspect-ratio(设备宽高比)
* ### 是否接受min/max前缀: 是
* ### 描述了输出设备的宽高比。该值包含两个以“/”分隔的正整数。代表了水平像素数（第一个值）与垂直像素数（第二个值）的比例。
```css
@media screen and (device-aspect-ratio: 16/9), screen and (device-aspect-ratio: 16/10){
  /* ... */
}
```

## device-height(设备高度)
* ### 是否接受 min/max 前缀：是
* ### 描述了输出设备的高度（整个屏幕或页的高度，而不是仅仅像文档窗口一样的渲染区域）。

## device-width(设备宽度)
* ### 是否接受 min/max 前缀：是
* ### 描述了输出设备的宽度（整个屏幕或页的宽度，而不是仅仅像文档窗口一样的渲染区域）。

## height(高度)
* ### 是否接受 min/max 前缀：是
* ### height 媒体属性描述了输出设备渲染区域（如可视区域的高度或打印机纸盒的高度）的高度。

## width(宽度)
* ### 是否接受 min/max 前缀：是
* ### width 媒体属性描述了输出设备渲染区域（如可视区域的宽度或打印机纸盒的宽度）的宽度。

## orientation(方向)
* ### 值: landscape(横屏) | portrait(竖屏)
* ### 是否接受 min/max 前缀：否
* ### 指定了设备处于横屏（宽度大于高度）模式还是竖屏（高度大于宽度）模式。

## resolution(分辨率)
* ### 是否接受 min/max 前缀：是
* ### 指定输出设备的分辨率（像素密度）。分辨率可以用每英寸（dpi）或每厘米（dpcm）的点数来表示。
```css
@media print and (min-resolution: 300dpi){
  /* ... */
}
/* 下面等价于老语法: (min-device-pixel-ratio: 2) */
@media screen and (min-resolution: 2dppx){
  /* ... */
}
```


