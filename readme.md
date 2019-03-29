# mdx-deck [![explain]][source] [![translate-svg]][translate-list]

[explain]: http://llever.com/explain.svg
[source]: https://github.com/chinanf-boy/mdx-deck-explain
[translate-svg]: http://llever.com/translate.svg
[translate-list]: https://github.com/chinanf-boy/chinese-translate-list

「 基于[MDX][]的网页幻灯片 」

[中文](./readme.md) | [english](.https://github.com/jxnblk/mdx-deck)

---

## 校对 🀄️

<!-- doc-templite START generated -->
<!-- repo = 'jxnblk/mdx-deck' -->
<!-- time = '2018 9.15' -->
<!-- commit = 'f7aac5e2ca1c1cf66f6e0b1961b066933ea8bf7d' -->
翻译的原文 | 与日期 | 最新更新 | 更多
---|---|---|---
[commit] | ⏰ 2018 9.15 | ![last] | [中文翻译][translate-list]

[last]: https://img.shields.io/github/last-commit/jxnblk/mdx-deck.svg
[commit]: https://github.com/jxnblk/mdx-deck/tree/f7aac5e2ca1c1cf66f6e0b1961b066933ea8bf7d

<!-- doc-templite END generated -->

- [x] [readme.md](./readme.md)
- [ ] [docs](./docs)

### 贡献

欢迎 👏 勘误/校对/更新贡献 😊 [具体贡献请看](https://github.com/chinanf-boy/chinese-translate-list#贡献)

## 生活

[If help, **buy** me coffee —— 营养跟不上了，给我来瓶营养快线吧! 💰](https://github.com/chinanf-boy/live-need-money)

---

### 目录

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [mdx-deck](#mdx-deck)
  - [入门](#%E5%85%A5%E9%97%A8)
  - [视频和文章](#%E8%A7%86%E9%A2%91%E5%92%8C%E6%96%87%E7%AB%A0)
  - [快速开始](#%E5%BF%AB%E9%80%9F%E5%BC%80%E5%A7%8B)
  - [使用 MDX](#%E4%BD%BF%E7%94%A8-mdx)
    - [导入](#%E5%AF%BC%E5%85%A5)
  - [主题化](#%E4%B8%BB%E9%A2%98%E5%8C%96)
    - [内置主题](#%E5%86%85%E7%BD%AE%E4%B8%BB%E9%A2%98)
    - [自定义主题](#%E8%87%AA%E5%AE%9A%E4%B9%89%E4%B8%BB%E9%A2%98)
    - [组件](#%E7%BB%84%E4%BB%B6)
    - [库](#%E5%BA%93)
    - [布局](#%E5%B8%83%E5%B1%80)
    - [内置布局](#%E5%86%85%E7%BD%AE%E5%B8%83%E5%B1%80)
  - [演示者模式](#%E6%BC%94%E7%A4%BA%E8%80%85%E6%A8%A1%E5%BC%8F)
    - [演讲者笔记](#%E6%BC%94%E8%AE%B2%E8%80%85%E7%AC%94%E8%AE%B0)
  - [概述模式](#%E6%A6%82%E8%BF%B0%E6%A8%A1%E5%BC%8F)
  - [键盘快捷键](#%E9%94%AE%E7%9B%98%E5%BF%AB%E6%8D%B7%E9%94%AE)
  - [导出](#%E5%AF%BC%E5%87%BA)
  - [CLI 选项](#cli-%E9%80%89%E9%A1%B9)
  - [文件](#%E6%96%87%E4%BB%B6)
  - [例子](#%E4%BE%8B%E5%AD%90)
    - [有关](#%E6%9C%89%E5%85%B3)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# mdx-deck

![](https://s3.amazonaws.com/jxnblk/mdx-deck.gif)

[MDX][]的网页幻灯片

[![Build Status][badge]][travis]
[![Version][version-badge]][npm]
[![Downloads][downloads-badge]][npm]

[badge]: https://img.shields.io/travis/jxnblk/mdx-deck.svg?style=flat-square
[travis]: https://travis-ci.org/jxnblk/mdx-deck
[version-badge]: https://img.shields.io/npm/v/mdx-deck.svg?style=flat-square
[downloads-badge]: https://img.shields.io/npm/dw/mdx-deck.svg?style=flat-square
[npm]: https://npmjs.com/package/mdx-deck

```sh
npm i -D mdx-deck
```

- :memo: 在markdown时写下演示文稿
- :atom_symbol: 导入并使用[React组件](#imports)
- :nail_care: 可定制[主题](#theming)和组件
- :zero: 零配置 CLI
- :tipping_hand_woman: [演示者模式](#presenter-mode)
- :notebook: [演讲者说明](#speaker-notes)

[查看演示](https://jxnblk.com/mdx-deck)

## 入门

创建一个[MDX][]文件并用`---`将每张幻灯片分开.

````mdx
# This is the title of my deck
---
# About Me
---
```jsx
<CodeSnippet />
```
---
import Demo from './components/Demo'

<Demo />
---
# The end
````

您的`package.json`添加运行脚本,用 mdx-deck CLI 指向`.mdx`文件以启动开发服务器:

```json
"scripts": {
  "start": "mdx-deck deck.mdx"
}
```

启动开发服务器:

```sh
npm start
```

## 视频和文章

- [Egghead 教程][egghead]来自[Andrew Del Prete](https://github.com/andrewdelprete).
- [mdx-deck: 由 markdown和React驱动的幻灯片][kcd-medium] by [Kent C. Dodds][]
- [使用 MDX-Deck 制造 快 & 漂亮演讲 ][hw-video] by [Harry Wolff][] ([例子][hw-demo])
- [什么是 MDX][kcd-video] by [Kent C. Dodds][]

[egghead]: https://egghead.io/lessons/react-build-a-slide-deck-with-mdx-deck-using-markdown-react
[kent c. dodds]: https://mobile.twitter.com/kentcdodds
[kcd-video]: http://youtu.be/d2sQiI5NFAM?a
[kcd-medium]: https://blog.kentcdodds.com/mdx-deck-slide-decks-powered-by-markdown-and-react-bfc6d6af20da
[hw-video]: https://www.youtube.com/watch?v=LvP2EqCiQMg&feature=youtu.be
[hw-demo]: https://github.com/hswolff/mdx-deck-demo
[harry wolff]: https://mobile.twitter.com/hswolff

## 快速开始

要创建零配置的新演示文稿,在新文件夹中请运行以下命令,生成演示文稿幻灯片:

```sh
npm init deck my-presentation-name
```

## 使用 MDX

MDX 可以使用 Markdown 语法,并使用 JSX 呈现 React 组件.

### 导入

要导入组件,请使用 ES 导入语法,使用任何 markdown 或 JSX 语法中的空行分隔.


```mdx
import { Box } from 'grid-styled'

<Box color='tomato'>
  Hello
</Box>
```

阅读更多关于 MDX 语法的内容

MDX 文档[.][mdx]

## 主题化

mdx-deck 使用 [styled-components] 用于风格主题 - 几乎可以使演示文稿的任何部分主题化

### 内置主题

<div>
  <img src='docs/images/future.png' width='256' />
  <img src='docs/images/comic.png' width='256' />
  <img src='docs/images/yellow.png' width='256' />
</div>

mdx-deck 包含几个内置主题,用于更改演示文稿的外观和风格.

导出`theme`, 在您的 MDX 文件中启用主题.

```mdx
export { dark as theme } from 'mdx-deck/themes'

# Dark Theme
```

MDX 使用[导出](https://github.com/mdx-js/mdx#exports)作为文件与其父组件通信的一种方式.有关可用主题的列表,请参阅[主题文件](docs/themes.zh.md).

### 自定义主题

可以来自导出来自 MDX 文件的自定义主题`theme`.

```mdx
export { default as theme } from './theme'

# Hello
```

主题应该是一个对象,其中包含各个组件的字体,颜色和 CSS 字段.建议所有自定义主题,都将默认主题扩展作为基础.

```js
// example theme.js
import theme from 'mdx-deck/themes';

export default {
  // extends the default theme
  ...theme,
  // add a custom font
  font: 'Roboto, sans-serif',
  // custom colors
  colors: {
    text: '#f0f',
    background: 'black',
    link: '#0ff'
  }
};
```

阅读更多关于[主题内容的文档](docs/theming.zh.md)

### 组件

mdx-deck 包含有助于创建演示文稿的内置组件,包括全屏图像组件,允许单步滑动部分的 Appear 组件,以及用于添加演讲者笔记的 Notes 组件.

阅读更多[组件文档](docs/components.zh.md)内容.

### 库

这些第三方库非常适合与 mdx-deck 一起使用.

- [CodeSurfer][]:用于滚动,缩放和突出显示代码的 React 组件.

[codesurfer]: https://github.com/pomber/code-surfer

### 布局

每张幻灯片都可以自定义围绕其内容的布局.这可以用作其他演示应用程序和库中的幻灯片模板的替代品.

```js
// example Layout.js
import React from 'react';

export default ({children}) => (
  <div
    style={{
      width: '100vw',
      height: '100vw',
      backgroundColor: 'tomato'
    }}
  >
    {children}
  </div>
);
```

```mdx
import Layout from './Layout'

# No Layout

---
export default Layout

# Custom Layout
```

在该幻灯片中,布局组件包装 MDX 元素,这意味着您可以使用 CSS-in-JS 嵌套的 ThemeProvider 或目标元素.

### 内置布局

mdx-deck 包含一些内置布局,用于反转主题颜色和更改幻灯片的布局.了解更多[内置布局](docs/components.zh.md#layouts).

## 演示者模式

mdx-deck 包含一个内置的演示者模式,可以预览下一张幻灯片和一个计时器.

![presenter mode screenshot](docs/images/presenter-mode.png)

要使用演示者模式:

- 在同一浏览器中打开两个窗口,在两个不同的屏幕上使用相同的 URL.(这应该适用于开发和导出的演示文稿)
- 在你的窗口按下`Option + P`(`Alt + P`)键进入演示者模式.
- 在屏幕上显示其他窗口供观众查看.
- 使用向左和向右箭头键从窗口控制演示文稿; 另一个窗口应保持同步

### 演讲者笔记

只在演示者模式下,笔记才显示在幻灯片中.演讲者笔记可以来自以下两种方式之一添加:

**markdown:** 使用`notes` - 代码区块中的语言属性,用于添加演讲者笔记.

````mdx
# Slide Content

```notes
These are only visible in presenter mode
```
````

**备注组件:** 使用`Notes`组件创建更复杂的演讲者笔记.

```mdx
import { Notes } from 'mdx-deck'

# Slide Content

<Notes>
  Only visible in presenter mode
</Notes>
```

## 概述模式

![Overview Mode](docs/images/overview-mode.png)

编辑幻灯片时,使用`Option + O`切换概览模式.这将显示左侧所有幻灯片的列表以及右侧当前幻灯片的预览.

## 键盘快捷键

| 键       | 描述                                     |
| -------- | ---------------------------------------- |
| 左箭头   | 转到上一张幻灯片(或回退[Appear][])     |
| 右箭头   | 转到下一张幻灯片(或进入[Appear][])         |
| 空格     | 转到下一张幻灯片(或进入[Appear][])         |
| 向上箭头 | 回退[Appear][]组件,没有导航 |
| 向下箭头 | 下一步[Appear][]组件,没有导航   |
| Option + P | 切换[演示者模式](#演示者模式)        |
| Option + O | 切换[概述模式](#概述模式)           |
| Option + G | 切换网格视图模式                         |

> `Appear` 相当于单张幻灯片中点一次就出现的一行的列表组

[appear]: docs/components.zh.md#appear

## 导出

你的`package.json`添加一个`build`脚本, 演示文稿导出为 HTML, 带有JS 包.

```json
"scripts": {
  "build": "mdx-deck build deck.mdx"
}
```

查看更多导出选项[导出文档](docs/exporting.zh.md)

## CLI 选项

```
-p --port     开发服务器端口
--no-open     阻止在默认浏览器中打开
-d --out-dir  导出的输出目录
--no-html     禁用静态HTML呈现
--out-file    屏幕截图或PDF导出的文件名
--width       宽度-像素px
--height      高度-像素px
--webpack     webpack配置文件的路径
```

## 文件

- [主题化](docs/theming.zh.md)
- [内置主题](docs/themes.zh.md)
- [布局](docs/layouts.zh.md)
- [组件](docs/components.zh.md)
- [导出](docs/exporting.zh.md)
- [高级用法](docs/advanced.zh.md)
- [React API](docs/react.zh.md)

## 例子

- [设计系统与React][design-systems-react]来自[Diana Mount](https://mobile.twitter.com/broccolini)
- [现在,将巴西带入云端][brazil-now]来自[吉列尔莫·劳赫](https://mobile.twitter.com/rauchg/)
- [简化React][simplify-react]来自[肯特 C.多德斯](https://mobile.twitter.com/kentcdodds)
- [我有 99 个问题,但 GraphQL 不是一个][99-problems]来自[萨拉维埃拉](https://mobile.twitter.com/NikkitaFTW)

---

### 有关

- [MDX][]
- [mdx-go][]
- [ok-mdx][]
- [Compositor x0][]
- [styled-components][]
- [styled-system][]
- [Spectacle][]

[MIT 许可证](LICENSE.md)

[mdx]: https://github.com/mdx-js/mdx
[ok-mdx]: https://github.com/jxnblk/ok-mdx
[compositor x0]: https://github.com/c8r/x0
[styled-system]: https://github.com/jxnblk/styled-system
[styled-components]: https://github.com/styled-components/styled-components
[spectacle]: https://github.com/FormidableLabs/spectacle
[mdx-go]: https://github.com/jxnblk/mdx-go

<!-- examples -->

[design-systems-react]: https://github-ds.now.sh/#0
[brazil-now]: https://braziljs.now.sh
[simplify-react]: https://simply-react.netlify.com/#0
[99-problems]: https://99-problems-graphql-aint-one.now.sh/#0
