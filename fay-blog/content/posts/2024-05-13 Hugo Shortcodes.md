---
title: Hugo 自带短代码 Shortcodes
date: 2024-05-13
tags:
  - Hugo
  - 折腾
categories: Hugo
keywords:
  - Hugo
  - 折腾
---
## figure

```html
{\{< figure src="/images/lighthouse.jpg" title="Lighthouse (figure)" >}} //去掉"\"
```


效果：
![image.png](https://img.i-fay.com/blog-pic/2024/05/b6a151c15bb8f27e76abc816bf8c0e6b.png)


## gist

```java
{\{< gist spf13 7896402 >}} //去掉"\"
```

效果：
{{< gist spf13 7896402 >}}
## vimeo

```java
{\{< vimeo 146022717 >}} //去掉"\"
```

效果：
{{< vimeo 146022717 >}}
## youtube

```java
{\{< youtube w7Ft2ymGmfc >}} //去掉"\"
```

效果：
{{< youtube w7Ft2ymGmfc >}}

