# Frontmatter

> 更新时间：2024-1-28

Vitepress已经给了一个配置，就在我们的 `docs - index.md` 中

::: details 官方配置示例
```yaml
---
layout: home

hero:
  name: "My Awesome Project"
  text: "A VitePress Site"
  tagline: My great project tagline
  actions:
    - theme: brand
      text: Markdown Examples
      link: /markdown-examples
    - theme: alt
      text: API Examples
      link: /api-examples

features:
  - title: Feature A
    details: Lorem ipsum dolor sit amet, consectetur adipiscing elit
  - title: Feature B
    details: Lorem ipsum dolor sit amet, consectetur adipiscing elit
  - title: Feature C
    details: Lorem ipsum dolor sit amet, consectetur adipiscing elit
---
```
:::

## 基本示例

包含语言/标题/自定义标题/站点描述

```yaml
---
lang: zh-CN
title: VitePress
titleTemplate: Vite 和 Vue 强力驱动的静态网站生成器
description: 简单、强大、快速。满足你一直想要的现代SSG框架
---
```




## head

指定要为当前页面注入的额外头标签。将附加在站点级配置注入的头标签之后

```yaml
---
head:
  - - meta
    - name: description
      content: hello
  - - meta
    - name: keywords
      content: super duper SEO
---
```



## 首页

`home` 就是首页 ，`doc` 是文档页，`page` 是无样式的文档，自定义页面

::: tip 说明
个人建议还是要首页的好，视觉效果强

你也可以通过 `layout: false` 直接关闭样式
:::

```yaml
---
layout: home
---
```


## hero

就是我们网站的居中文案，都比较简单

::: tip 关于actions
`theme: brand` 为主要的按钮，还有 `alt` `sponsor`

`text: 开始` 文字可以自定义

`link: /getting-started` 跳转的路径
:::


```yaml
---
hero:
  name: VitePress
  text: "快速上手中文教程"
  tagline: 如果你也想搭建它，那跟我一起做吧
  image:
    src: /logo.png
    alt: VitePress
  actions:
    - theme: brand
      text: 开始
      link: /getting-started
    - theme: alt
      text: GitHub
      link: https://github.com/vuejs/vitepress
---
```

::: warning 关于hero的文字及logo添加渐变色

不推荐直接用 `<style>` 标签，因为build后样式会丢失

建议在css文件中添加并引用 [👆 点我查看美化方法](./style#主题色)
:::


## Features

特性可以使用emoji表情、图片以及SVG创建图形

::: tip 说明
* Emoji大全：https://www.emojiall.com/zh-hans/

* 图片：直接引用，也可以使用明暗色图区别开

* SVG图形：[iconfont](https://www.iconfont.cn/)、[xicons](https://www.xicons.org/#/zh-CN)、[iconpark](https://iconpark.oceanengine.com/official)
:::


```yaml
---
features:
  - icon: 📝
    title: 专注于您的内容
    details: 只需使用 Markdown 即可轻松创建精美的文档网站
  - icon: 
      dark: /logo.png
      light: /logo-light.png
    title: 享受Vite DX
    details: Instant server start, lightning fast hot updates, and leverage Vite ecosystem plugins.
  - icon: <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32"><path fill="#41b883" d="M24.4 3.925H30l-14 24.15L2 3.925h10.71l3.29 5.6 3.22-5.6Z"/><path fill="#41b883" d="m2 3.925 14 24.15 14-24.15h-5.6L16 18.415 7.53 3.925Z"/><path fill="#35495e" d="M7.53 3.925 16 18.485l8.4-14.56h-5.18L16 9.525l-3.29-5.6Z"/></svg>
    title: 使用 Vue 进行定制
    details: 直接在 Markdown 中使用 Vue 语法和组件，或使用 Vue 构建自定义主题
  - icon: 🚀
    title: 快速发布网站
    details: 使用静态 HTML 进行快速初始加载，使用客户端路由进行快速加载后导航
---
```

如果你想做跳转也是可以的，我们添加一个 `link` 和 `linkText`


```yaml{11-12}
---
features:
  - icon: 📝
    title: 专注于您的内容
    details: 只需使用 Markdown 即可轻松创建精美的文档网站
  - icon: 
      dark: /logo.png
      light: /logo-light.png
    title: 享受Vite DX
    details: Instant server start, lightning fast hot updates, and leverage Vite ecosystem plugins.
    link: https://vitejs.cn/ // [!code focus:2]
    linkText: Vite
  - icon: <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32"><path fill="#41b883" d="M24.4 3.925H30l-14 24.15L2 3.925h10.71l3.29 5.6 3.22-5.6Z"/><path fill="#41b883" d="m2 3.925 14 24.15 14-24.15h-5.6L16 18.415 7.53 3.925Z"/><path fill="#35495e" d="M7.53 3.925 16 18.485l8.4-14.56h-5.18L16 9.525l-3.29-5.6Z"/></svg>
    title: 使用 Vue 进行定制
    details: 直接在 Markdown 中使用 Vue 语法和组件，或使用 Vue 构建自定义主题
  - icon: 🚀
    title: 快速发布网站
    details: 使用静态 HTML 进行快速初始加载，使用客户端路由进行快速加载后导航
---
```


## 导航栏

默认 `true` 开启，可以选择关闭

```yaml
---
navbar: false
---
```



## 侧边栏

默认 `true` 开启，可以选择关闭

```yaml
---
sidebar: false
---
```


## 大纲

侧边大纲默认在右侧 ，通过 `aside` 设置左侧或关闭，默认 `true`

```yaml
---
aside: left
---
```

```yaml
---
aside: false
---
```

右侧的大纲，默认显示是二级标题，通过设置 `outline` 实现多级标题

::: warning 注意
设置到六级标题可以用 `'deep'` ，关闭 `false`

此设置与 [页面中的大纲](./page.md#大纲) 设置相同，会覆盖！
:::

```yaml
---
outline: [2,3]
---
```

想要当前页不显示

```yaml
---
outline: false
---
```



## 上次更新

默认开启，不想显示可以关闭

```yaml
---
lastUpdated: false
---
```



## 编辑本页

默认开启，不想显示可以关闭

```yaml
---
editLink: false
---
```


## 上/下页

默认从侧边栏配置中读取，也可以指定在上/下页显示的文本/链接

::: warning 注意
`prev` 表示上一页

`next` 表示下一页
:::

### 更改文字显示

仅更改上/下页显示的文字，跳转还是按照侧边栏配置的读取的


```yaml
---
prev: '页面 | 更详细的页面配置'
next: 'Markdown | 更详细的markdown'
---
```


### 更改跳转链接

可更改成任意自己想跳转的文章

```yaml
---
prev:
  text: '页面'
  link: '/page'
next:
  text: 'Markdown'
  link: '/markdown'
---
```

### 关闭上/下页

不想显示可以选择关闭

```yaml
---
prev: false
next: false
---
```


## 页脚

不想显示可以选择关闭

```yaml
---
footer: false
---
```


## PageClass

在特定页面添加额外的类名

```yaml
---
pageClass: custom-page-class
---
```

然后，你可以在特定页面中自定义样式，路径 `.vitepress/theme/custom.css`

```css
.custom-page-class {
  /* page-specific styles */
}
```


## 我的配置参考


::: details 点击查看我的完整配置
```md
---
layout: home

hero:
  name: VitePress
  text: "快速上手中文教程"
  tagline: 如果你也想搭建它，那跟我一起做吧
  image:
    src: /logo.png
    alt: VitePress
  actions:
    - theme: brand
      text: 开始
      link: /getting-started
    - theme: alt
      text: GitHub
      link: https://github.com/vuejs/vitepress
    - theme: sponsor
      text: 视频介绍
      link: 
    - theme: sponsor
      text: 相关资料
      link: 

features:
  - icon: 📝
    title: 专注于您的内容
    details: 只需使用 Markdown 即可轻松创建精美的文档网站
  - icon: 
      dark: /vitepress.png
      light: /vitepress-light.png
    title: 享受Vite DX
    details: 即时服务器启动，闪电般快速的热更新，并利用 Vite 生态插件
    link: https://vitejs.cn/
    linkText: Vite
  - icon: <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32"><path fill="#41b883" d="M24.4 3.925H30l-14 24.15L2 3.925h10.71l3.29 5.6 3.22-5.6Z"/><path fill="#41b883" d="m2 3.925 14 24.15 14-24.15h-5.6L16 18.415 7.53 3.925Z"/><path fill="#35495e" d="M7.53 3.925 16 18.485l8.4-14.56h-5.18L16 9.525l-3.29-5.6Z"/></svg>
    title: 使用 Vue 进行定制
    details: 直接在 Markdown 中使用 Vue 语法和组件，或使用 Vue 构建自定义主题
  - icon: 🚀
    title: 快速发布网站
    details: 使用静态 HTML 进行快速初始加载，使用客户端路由进行快速加载后导航
---

```
:::






