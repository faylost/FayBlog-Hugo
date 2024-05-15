---
title: Hugo 自定义文章样式
date: 2024-05-15
tags:
  - Hugo
  - 文章样式
categories: Hugo
keywords:
  - Hugo
  - 文章样式
  - 折腾
---
以文件夹形式进行文章分类，并以此为判断条件。


```
content
├── posts
│   ├── chat
│   ├── coding
│   ├── daily
│   ├── reading
```

代码示例：
利用 Hugo 的 [.File.Dir](https://gohugo.io/variables/files/) 和 [replaceRE](https://gohugo.io/functions/replacere/) 正则。

```html
{{ $PostCate := .File.Dir | replaceRE "posts/(.*)/" "$1"}}
{{ if eq $PostCate "chat"}}
    <div class="post-meta">
        {{ if .Date }}
            <span class="post-date">{{ .Date.Format | default "2006-01-02" }}</span>
        {{ end }}
    </div>
    <div class="post-content">
        <a href="{{ .Permalink }}"><img loading="lazy" class="avatar" src=https://gravatar.loli.net/avatar/{{ md5 "自己的邮箱" }} ></a>
        {{ .Content }}
    </div>
{{ else }}
    ……正常文章样式
{{ end }}

```

一般修改 `_default/list.html` 和 `_default/single.html`，其中 list 是放在文章列表的 `{{rang ……}}` 循环之中。

`.File.Dir` 是获取当前文章的相对路径，`replaceRE "posts/(.*)/" "$1"` 是正则到子文件夹名，之后 `{{ if eq $PostCate "chat"}}` 就是判断。