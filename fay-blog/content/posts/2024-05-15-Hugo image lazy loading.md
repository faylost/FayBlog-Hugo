---
title: Hugo 图片懒加载
date: 2024-05-15
tags:
  - Hugo
  - 折腾
  - 懒加载
categories: Hugo
keywords:
  - Hugo
  - 折腾
  - 懒加载
---
官方说明 [#render-hook-templates](https://gohugo.io/getting-started/configuration-markup/#render-hook-templates)，Hugo v0.62+

对 md 内的链接（link）和图像（image）自定义渲染，只需在主题新建 `layouts/_default/_markup/render-image.html`

```html
layouts/_default
├── _markup
│   └── render-image.html
```

代码：

```html
<p class="md_image">
  <img loading='lazy' src="{{ .Destination | safeURL }}" alt="{{ .Text }}" {{ with .Title}} title="{{ . }}"{{ end }} />
</p>
```
