# Curtain Card

[![hacs_badge](https://img.shields.io/badge/HACS-Custom-orange.svg)](https://github.com/custom-components/hacs)
[![Stable](https://img.shields.io/github/v/release/georgezhao2010/lovelace-curtain-card)](https://github.com/georgezhao2010/lovelace-curtain-card/releases/latest)

English | [简体中文](https://github.com/georgezhao2010/lovelace-toggle-control-button/blob/main/README_hans.md)

Curtain card for Home Assistant Lovelace UI.

It is suitable for curtain opening horizontally. You can customize the opening direction of curtain and the scenery image outside the window. The curtain can be opened or closed by dragging it by hand or mouse, to a specified position by a specified percentage. 

# Installation

The easiest way to do this is to install it in HACS as a custom repository.

If you don't use HACS, you can also install it manually by following these steps. 

Download and copy `dist/curtain-card.js` to `/config/www/` directory in your home Assistant

Add the following configuration to the resources items and change the path to the exact location of your file. 

```
  - url: /local/curtain-card.js
    type: module
```

# Options

| Name | Type | Required | Default| Description
| --- | --- | --- | --- | --- |
| entity | String | Yes | none | entity_id |
| type | String | Yes | none | custom:curtain-card |
| title | String | No | none | The title displayed on the card only appeared when it was set |
| curtainColor | String | No | none | Curtain color, expressed in 4-channel RGB |
| direction | String | No | 'left' | |Direction of curtain opening |
| sceneImage | String | No | none | The image URL of the scene outside the window |
| showStatus | Boolean | No | true | Whether to display percentage and opening/closing status information at the bottom of card|
| invertPercentage | Boolean | No | false | invert the percentage |


## curtainColor option

curtainColor is represented by 4 channel RGB colors, red, green, blue and Alpha channel respectively. In Alpha channel you should set certain transparency to display the texture of the curtain. Specific adjustment can be made according to the color of the your curtain. 

## sceneImage option

SceneImage should be an 800*680 scale image, 400*340 resolution is recommended, PNG/JPEG, or even GIF GIF. 

# Examples
## Example1

```
type: custom:curtain-card
entity: cover.XXXXXXXX_motor
title: 卧室窗帘
curtainColor: rgb(200,60,80,0.3)
direction: right
```

![Example1](curtain-1.gif)

## Example2

```
type: custom:curtain-card
entity: cover.0x00158d0004012897_motor
title: 客厅窗帘
curtainColor: rgb(26,160,220,0.5)
direction: left
sceneImage: /local/images/2.gif
```

![Example2](curtain-2.gif)

