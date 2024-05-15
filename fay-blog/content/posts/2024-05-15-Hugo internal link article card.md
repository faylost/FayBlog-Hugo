---
title: Hugo 文章内链卡片显示
date: 2024-05-15
tags:
  - Hugo
  - 折腾
  - 内链卡片
categories: Hugo
keywords:
  - Hugo
  - 折腾
  - 内链卡片
---
## 代码

创建 `/layouts/shortcodes/link.html`：

```html
{{$URL := .Get 0}}
{{ with .Site.GetPage $URL }}
<div class="post-preview">
  <div class="post-preview--meta" style="width:100%;">
    <div class="post-preview--middle">
      <h4 class="post-preview--title">
        <a target="_blank" href="{{ .Permalink }}">{{ .Title }}</a>
      </h4>
      <time class="post-preview--date">{{ .Date.Format ( default "2006-01-02") }}</time>
      {{ if .Params.tags }}
      <small>{{ range .Params.tags }}#{{ . }}&nbsp;{{ end }}</small>
      {{ end }}
      <section style="max-height:105px;overflow:hidden;" class="post-preview--excerpt">
        {{ .Summary | plainify}}
      </section>
    </div>
  </div>
</div>
{{ end }}

```

## 效果：

![image.png](https://img.i-fay.com/blog-pic/2024/05/78f2b705aad9a386336d89f3e7e9ec67.png)

==样式 CSS 代码需自行设置==
## 使用方式：

```java
{\{<link "bitcron-auto-article-refer">}} //去掉"\"
```

其中 `link` 匹配短代码模板 `link.html` ，之后填的 `bitcron-auto-article-refer` 是文章 md 的文件名。