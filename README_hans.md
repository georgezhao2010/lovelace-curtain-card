# Curtain Card

[![hacs_badge](https://img.shields.io/badge/HACS-Custom-orange.svg)](https://github.com/custom-components/hacs)
[![Stable](https://img.shields.io/github/v/release/georgezhao2010/lovelace-curtain-card)](https://github.com/georgezhao2010/lovelace-curtain-card/releases/latest)

[English](https://github.com/georgezhao2010/lovelace-toggle-control-button/blob/main/README.md) | 简体中文

Home Assistant Lovelace UI中使用的窗帘卡片。

适用于水平开启的窗帘，可以自定义窗帘打开方向，自定义窗外的景色图片。使用手/或者鼠标拖拽窗帘即可打开或者关闭窗帘，也可以拖拽到指定位置实现打开或者关闭指定的百分比。

# 安装

最简单的办法是在HACS中作为自定义仓库安装。

如果你不使用HACS，也可以按照以下方法进行手动安装。

将dist/curtain-card.js下载并复制到你的HomeAssistant的/config/www/目录中。

将如下配置加入"resources"配置项中，将路径改为你文件所在的具体位置。

```
  - url: /local/curtain-card.js
    type: module
```

# 卡片配置项
| 配置项 | 类型 | 必填 | 默认值 | 描述 |
| --- | --- | --- | --- | --- |
| entity | String | Yes | none | entity_id |
| type | String | Yes | none | custom:curtain-card |
| title | String | No | none | 卡片上显示的标题, 不设则不显示 |
| curtainColor | String | No | none | 窗帘颜色, 以4通道RGB表示 |
| direction | String | No | 'left' | 窗帘拉开方向 |
| sceneImage | String | No | none | 窗外场景的图片URL |
| showStatus | Boolean | No | true | 是否在底部显示开闭百分比和打开关闭状态信息 |
| invertPercentage | Boolean | No | false | 百分比翻转 |


## curtainColor 配置项

curtainColor用4通道RGB颜色表示，分别是红绿蓝及Alpha通道，Alpha应设置一定透明度以便显示窗帘的纹理，具体调整，可以根据家里窗帘颜色自己尝试。

## sceneImage 配置项

sceneImage图片最好是一个800*680比例的图片，推荐使用400*340分辨率的，可以是PNG/JPEG等，甚至是GIF动图。

# 示例
## 示例1

```
type: custom:curtain-card
entity: cover.XXXXXXXX_motor
title: 卧室窗帘
curtainColor: rgb(200,60,80,0.3)
direction: right
```

![Example1](curtain-1.gif)

## 示例2

```
type: custom:curtain-card
entity: cover.0x00158d0004012897_motor
title: 客厅窗帘
curtainColor: rgb(26,160,220,0.5)
direction: left
sceneImage: /local/images/2.gif
```

![Example2](curtain-2.gif)
