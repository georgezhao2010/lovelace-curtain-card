# Curtain Card

[![hacs_badge](https://img.shields.io/badge/HACS-Default-orange.svg)](https://github.com/hacs/integration)
[![Donate](https://img.shields.io/badge/donate-BuyMeCoffee-yellow.svg)](https://www.buymeacoffee.com/georgezhao2010)
[![Stable](https://img.shields.io/github/v/release/georgezhao2010/lovelace-curtain-card)](https://github.com/georgezhao2010/lovelace-curtain-card/releases/latest)

English | [简体中文](https://github.com/georgezhao2010/lovelace-curtain-card/blob/master/README_hans.md)

Curtain card for Home Assistant Lovelace UI, to control your motor of cover entities.

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

| Name | Type | Required | Default| Description|
| --- | --- | --- | --- | --- |
| entity | String | Yes | none | entity_id |
| type | String | Yes | none | custom:curtain-card |
| title | String | No | none | The title displayed on the card only appeared when it was set |
| curtainColor | String | No | none | Curtain color, expressed in 4-channel RGB |
| direction | String | No | 'right' | right\|left\|center |
| sceneImage | String | No | none | The image URL of the scene outside the window |
| showStatus | Boolean | No | true | Whether to display percentage and opening/closing status information at the bottom of card|
| invertPercentage | Boolean | No | false | invert the percentage |
| size | Number | No | 260 | The curtain size displayed in card |


## curtainColor option

curtainColor is represented by 4 channel RGB colors, red, green, blue and Alpha channel respectively. In Alpha channel you should set certain transparency to display the texture of the curtain. Specific adjustment can be made according to the color of the your curtain. 

## sceneImage option

SceneImage should be an 800x680 scale image, 400x340 resolution is recommended, PNG/JPEG, or even GIF GIF. 

## size
The value range is from 100 to 800, You can set it to an appropriate value depending on your UI style.

# Examples
## Example1

A right-opening curtain

```
type: custom:curtain-card
entity: cover.XXXXXXXX_motor
title: 卧室窗帘
curtainColor: rgb(200,60,80,0.3)
direction: left
```

![Example1](curtain-1.gif)

## Example2

A left-opening curtain with a customized scene image.

```
type: custom:curtain-card
entity: cover.xxxxxxxx_motor
title: 客厅窗帘
curtainColor: rgb(26,160,220,0.5)
sceneImage: /local/images/2.gif
```

![Example2](curtain-2.gif)

## Example3

Set the size value so that the cards shown in stacks.

```
type: horizontal-stack
cards:
  - type: custom:curtain-card
    entity: cover.xxxxxxxx_motor
    curtainColor: rgb(26,160,220,0.5)
    direction: right
    size: 150
    showStatus: false
  - type: custom:curtain-card
    entity: cover.xxxxxxxx_motor
    curtainColor: rgb(200,60,80,0.3)
    direction: left
    size: 150
    showStatus: false
```

![Example3](h-stack.png)



