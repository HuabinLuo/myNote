---
title: 原生微信小程序使用Font Awesome和Iconfont两种字体图标库
date: 2019-03-19 14:55:46
tags: wxss
categories: 微信小程序
---

# Font Awesome

1. 下载[Font Awesome](http://fontawesome.dashgame.com/)包

2. 解压包后，将需要使用的css文件更改为fontAwesome.wxss

3. 将fonts文件夹和fontAwesome.wxss，复制到微信小程序目录中

4. 在需要使用字体的页面wxss文件中引用fontAwesome.wxss

   ```css
   @import '路径/fontAwesome.wxss';
   ```

5. 修改fontAwesome.wxss中@font-face的访问路径，可以使用相对路径或者绝对路径。但需要注意的是，相对路径为相对使用字体页面的路径，而不是相对fontAwesome.wxss的路径。

   ```css
   @font-face {
       font-family: 'FontAwesome';
       src: url('相对使用字体页面的路径/fonts/fontawesome-webfont.eot?v=4.7.0');
       src: url('相对使用字体页面的路径/fonts/fontawesome-webfont.eot?#iefix&v=4.7.0') format('embedded-opentype'), url('相对使用字体页面的路径/fonts/fontawesome-webfont.woff2?v=4.7.0') format('woff2'), url('相对使用字体页面的路径/fonts/fontawesome-webfont.woff?v=4.7.0') format('woff'), url('相对使用字体页面的路径/fonts/fontawesome-webfont.ttf?v=4.7.0') format('truetype'), url('相对使用字体页面的路径/fonts/fontawesome-webfont.svg?v=4.7.0#fontawesomeregular') format('svg');
       font-weight: normal;
       font-style: normal;
   }
   ```

6. 最后，直接在页面wxml中根据官网示例使用即可，如：

   ```html
   <i class="fa fa-xxx"></i>
   ```

# Iconfont

1. 在[Iconfont](https://www.iconfont.cn/)中添加需要使用的图标入库

2. 直接下载素材或者添加到项目后再下载到本地

3. 解压包后，将iconfont.css更改为iconfont.wxss，更改后复制到微信小程序目录中

4. 在需要使用字体的页面wxss文件中引用iconfont.wxss

   ```css
   @import '路径/iconfont.wxss';
   ```

5. 最后，直接在页面wxml中根据示例使用即可，如：

   ```html
   <i class="iconfont icon-xxx"></i>
   ```