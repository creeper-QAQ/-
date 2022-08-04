# <img src="https://muiplayer.oss-cn-shanghai.aliyuncs.com/static/image/title_logo.png" />

<div>
    <a href="https://www.npmjs.com/package/mui-player" target="_blank"><img src="https://img.shields.io/npm/v/mui-player?label=mui%20player" /></a>
    <a href="https://www.npmjs.com/package/mui-player-desktop-plugin" target="_blank"><img src="https://img.shields.io/npm/v/mui-player-desktop-plugin?label=mui%20player%20desktop" /></a>
	<a href="https://www.npmjs.com/package/mui-player-mobile-plugin" target="_blank"><img src="https://img.shields.io/npm/v/mui-player-mobile-plugin?label=mui%20player%20mobile" /></a>
	<a href="https://github.com/muiplayer/hello-muiplayer/tree/master/dist/js" target="_blank"><img src="https://img.shields.io/badge/gzip%20size-18kb-brightgreen" /></a>
    <a href="https://github.com/muiplayer/hello-muiplayer/blob/master/LICENSE" target="_blank"><img src="https://img.shields.io/badge/license-MIT-brightgreen" /></a>
</div>

> 播放，专注，连接，分享和自由 🚩

![Desktop](https://muiplayer.oss-cn-shanghai.aliyuncs.com/static/image/desktopPreview.png)

![Mobile](https://muiplayer.oss-cn-shanghai.aliyuncs.com/static/image/mobile_preview.png)

<a href="https://muiplayer.js.org/" target="_blank">Docs</a> | <a href="https://muiplayer.js.org/zh/" target="_blank">中文文档</a>

## 介绍

MuiPlayer 是一款 HTML5 视频播放插件，其默认配置了精美可操作的的播放控件，涉及了常用的播放场景，例如全屏播放、播放快进、循环播放、音量调节等功能。

支持 mp4、m3u8、flv 等多种媒体格式播放，解决大部分兼容问题，同时适应在PC、手机端播放。

MuiPlayer 具有丰富的参数可以自定义播放器实例，通过轻松的配置即可完成自定义场景的视频播放。

## 特点

MuiPlayer 帮助我们解决了日常 H5 Video 应用开发中的常见的一些大量问题：

1. 各浏览器平台播放 ui 不能统一
2. ui 扩展之间以及状态处理容易产生冲突
3. 在不同环境下（android、ios、pc）针对 h5 video api 可能触发事件的时机尽不相同
4. 媒体格式存在各种兼容问题，muiplayer 处理了大多数在不同环境下播放的兼容问题
5. 重复踩踏在开发 h5 video 过程中的一些问题，我们提供了一套完好的解决方案，让编程员少走一些弯路

## 安装

使用 npm 安装：

```
npm i mui-player --save
```

使用 yarn 安装：

```
yarn add mui-player
```

## 使用

1、使用 script 标签引入：

```html
<!-- import basic style files mui-player.min.css -->
<link rel="stylesheet" type="text/css" href="css/mui-player.min.css"/>

<!-- import basic script mui-player.min.js -->
<script type="text/javascript" src="js/mui-player.min.js"></script>

<!-- Specify the player container -->
<div id="mui-player"></div>
```

或者使用模块管理器引入：

```js
import 'mui-player/dist/mui-player.min.css'
import MuiPlayer from 'mui-player'
```

2、定义播放器容器：

```html
<div id="mui-player"></div>
```

3、初始化构建播放器：

```js
// 初始化 MuiPlayer 插件，MuiPlayer 方法传递一个对象，该对象包括所有插件的配置
var mp = new MuiPlayer({
    container:'#mui-player',
    title:'Title',
    src:'./static/media/media.mp4',
})
```

以上就能为初始化构建一个具有默认配置控件的视频播放器，下面你可以阅读关于 MuiPlayer 的一些 API 基础配置选项。

前往 [参数API](https://muiplayer.js.org/zh/api/)

## 官方文档

- [官方首页](https://muiplayer.js.org/zh/)
- [API 参考](https://muiplayer.js.org/zh/guide/api.html)
- [PC 扩展插件](https://muiplayer.js.org/zh/guide/mui-player-desktop-plugin.html)
- [移动端扩展插件](https://muiplayer.js.org/zh/guide/mui-player-mobile-plugin.html)
- [基础演示](https://muiplayer.js.org/zh/demo/)

## 开始

启动此工程

```
npm install
npm start
```

## 免责声明

这是 MuiPlayer 的非商业版本，它不包含提供商业用途播放器的相同功能，但是开源版本依然可提供稳定的视频播放解决方案。在使用此之前，请务必了解该开源项目的软件许可证。如果您想获取商业应用播放器，请从官方下载 <u>[专业版应用插件](https://muiplayer.js.org/zh/joinUs/)</u>。

## 入群与咨询
QQ：3131244726


## ©️ Software License
[GNU GENERAL PUBLIC LICENSE](https://github.com/muiplayer/hello-muiplayer/blob/master/LICENSE)

Copyright (C) 2007 Free Software Foundation, Everyone is permitted to copy and distribute verbatim copies of this license document, but changing it is not allowed.


## ⭐ Stars

[![Stargazers repo roster for @muiplayer/hello-muiplayer](https://reporoster.com/stars/muiplayer/hello-muiplayer)](https://github.com/muiplayer/hello-muiplayer/stargazers)

## 👏 Forks

[![Forkers repo roster for @muiplayer/hello-muiplayer](https://reporoster.com/forks/muiplayer/hello-muiplayer)](https://github.com/muiplayer/hello-muiplayer/network/members)

