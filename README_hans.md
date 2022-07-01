# Curtain Card

[![hacs_badge](https://img.shields.io/badge/HACS-Custom-orange.svg)](https://github.com/custom-components/hacs)
[![Stable](https://img.shields.io/github/v/release/georgezhao2010/lovelace-curtain-card)](https://github.com/georgezhao2010/lovelace-curtain-card/releases/latest)

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
