# mdx-deck [![explain]][source] [![translate-svg]][translate-list] 

[explain]: http://llever.com/explain.svg
[source]: https://github.com/chinanf-boy/Source-Explain
[translate-svg]: http://llever.com/translate.svg
[translate-list]: https://github.com/chinanf-boy/chinese-translate-list
[size-img]: https://packagephobia.now.sh/badge?p=mdx-deck
[size]: https://packagephobia.now.sh/result?p=mdx-deck

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

### 贡献

欢迎 👏 勘误/校对/更新贡献 😊 [具体贡献请看](https://github.com/chinanf-boy/chinese-translate-list#贡献)

## 生活

[help me live , live need money 💰](https://github.com/chinanf-boy/live-need-money)

---

### 目录

<!-- START doctoc -->
<!-- END doctoc -->


# MDX甲板

![](https://s3.amazonaws.com/jxnblk/mdx-deck.gif)

[MDX][]基于演示的套牌

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

-   :备忘录:在降价时写下演示文稿
-   :atom_symbol:导入并使用[反应组件](#imports)
-   :nail_care:可定制[主题](#theming)和组件
-   :零:零配置CLI
-   :tipping_hand_woman:[演示者模式](#presenter-mode)
-   :笔记本:[演讲者说明](#speaker-notes)

[查看演示](https://jxnblk.com/mdx-deck)

## 入门

创建一个[MDX][]文件并将每张幻灯片分开`---`.

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

添加运行脚本到您的`package.json`用mdx-deck CLI指向`.mdx`文件以启动开发服务器:

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

-   [Egghead教程][egghead]通过[安德鲁德尔普雷特](https://github.com/andrewdelprete).
-   [mdx-deck:由降价驱动的幻灯片并做出反应][kcd-medium]通过[肯特C.多德斯使用MDXDeck进行快速美观的演示][]
-   [通过][hw-video]哈利沃尔夫[][]演示[)][hw-demo]什么是MDX
-   [通过][kcd-video]肯特C.多德斯[快速开始.][]

[egghead]: https://egghead.io/lessons/react-build-a-slide-deck-with-mdx-deck-using-markdown-react

[kent c. dodds]: https://mobile.twitter.com/kentcdodds

[kcd-video]: http://youtu.be/d2sQiI5NFAM?a

[kcd-medium]: https://blog.kentcdodds.com/mdx-deck-slide-decks-powered-by-markdown-and-react-bfc6d6af20da

[hw-video]: https://www.youtube.com/watch?v=LvP2EqCiQMg&feature=youtu.be

[hw-demo]: https://github.com/hswolff/mdx-deck-demo

[harry wolff]: https://mobile.twitter.com/hswolff

## 要创建零配置的新演示文稿,请运行以下命令以在新文件夹中生成演示文稿套牌:

使用MDX

```sh
npm init deck my-presentation-name
```

## MDX可以使用Markdown语法并使用JSX呈现React组件.

进口

### 要导入组件,请使用ES导入语法,使用任何markdown或JSX语法中的空行分隔.

阅读更多关于MDX语法的内容

```mdx
import { Box } from 'grid-styled'

<Box color='tomato'>
  Hello
</Box>
```

MDX文档[.][mdx]主题化

## mdx-deck使用

风格组件[用于造型-几乎可以使演示文稿的任何部分成为主题][]内置主题

### mdx-deck包含几个内置主题,用于更改演示文稿的外观和风格.

<div>
  <img src='docs/images/future.png' width='256' />
  <img src='docs/images/comic.png' width='256' />
  <img src='docs/images/yellow.png' width='256' />
</div>

出口`theme`从您的MDX文件中启用主题.

```mdx
export { dark as theme } from 'mdx-deck/themes'

# Dark Theme
```

MDX使用[出口](https://github.com/mdx-js/mdx#exports)作为文件与其父组件通信的一种方式.有关可用主题的列表,请参阅[主题文件](docs/themes.md).

### 自定义主题

可以通过导出提供自定义主题`theme`来自MDX文件.

```mdx
export { default as theme } from './theme'

# Hello
```

主题应该是一个对象,其中包含各个组件的字体,颜色和CSS字段.建议所有自定义主题都将默认主题扩展为基础.

```js
// example theme.js
import theme from 'mdx-deck/themes'

export default {
  // extends the default theme
  ...theme,
  // add a custom font
  font: 'Roboto, sans-serif',
  // custom colors
  colors: {
    text: '#f0f',
    background: 'black',
    link: '#0ff',
  }
}
```

阅读更多关于主题的内容[主题文档](docs/theming.md)

### 组件

mdx-deck包含有助于创建演示文稿的内置组件,包括全屏图像组件,允许单步滑动部分的Appear组件,以及用于添加演讲者备注的Notes组件.

阅读更多内容[组件文档](docs/components.md).

### 图书馆

这些第三方库非常适合与mdx-deck一起使用.

-   [CodeSurfer][]:用于滚动,缩放和突出显示代码的React组件.

[codesurfer]: https://github.com/pomber/code-surfer

### 布局

每张幻灯片都可以包含围绕其内容的自定义布局.这可以用作其他演示应用程序和库中的幻灯片模板的替代品.

```js
// example Layout.js
import React from 'react'

export default ({ children }) =>
  <div
    style={{
      width: '100vw',
      height: '100vw',
      backgroundColor: 'tomato'
    }}>
    {children}
  </div>
```

```mdx
import Layout from './Layout'

# No Layout

---
export default Layout

# Custom Layout
```

布局组件将MDX元素包装在该幻灯片中,这意味着您可以使用CSS-in-JS嵌套的ThemeProvider或目标元素.

### 内置布局

mdx-deck包含一些内置布局,用于反转主题颜色和更改幻灯片的布局.了解更多[内置布局](docs/components.md#layouts).

## 演示者模式

mdx-deck包含一个内置的演示者模式,可以预览下一张幻灯片和一个计时器.

![presenter mode screenshot](docs/images/presenter-mode.png)

要使用演示者模式:

-   在同一浏览器中打开两个窗口,在两个不同的屏幕上使用相同的URL.(这应该适用于开发和导出的演示文稿)
-   在你的窗口按下`Option + P`(`Alt + P`)键进入演示者模式.
-   在屏幕上显示其他窗口供观众查看.
-   使用向左和向右箭头键从窗口控制演示文稿;另一个窗口应保持同步

### 演讲者备注

只能在演示者模式下显示的注释可以添加到任何幻灯片中.演讲者备注可以通过以下两种方式之一添加:

**降价:**使用`notes`隔离代码块中的语言属性,用于添加说话者注释.

````mdx
# Slide Content

```notes
These are only visible in presenter mode
```
````

**备注组件:**使用`Notes`组件创建更复杂的演讲者笔记.

```mdx
import { Notes } from 'mdx-deck'

# Slide Content

<Notes>
  Only visible in presenter mode
</Notes>
```

## 概述模式

![Overview Mode](docs/images/overview-mode.png)

编辑幻灯片时,使用切换概览模式`Option + O`.这将显示左侧所有幻灯片的列表以及右侧当前幻灯片的预览.

## 键盘快捷键

| 键      | 描述                         |
| ------ | -------------------------- |
| 左箭头    | 转到上一张幻灯片(或单步执行[出现][])      |
| 右箭头    | 转到下一张幻灯片(或进入[出现][])        |
| 空间     | 转到下一张幻灯片(或进入[出现][])        |
| 向上箭头   | 隐藏当前步骤[出现][]没有导航幻灯片的组件     |
| 向下箭头   | 显示下一步[出现][]没有导航幻灯片的组件      |
| 选项+ P. | 切换[演示者模式](#presenter-mode) |
| 选项+ O. | 切换[概述模式](#overview-mode)   |
| 选项+ G. | 切换网格视图模式                   |

[appear]: docs/components.md#appear

## 出口

添加一个`build`脚本给你`package.json`使用JS包将演示文稿导出为HTML.

```json
"scripts": {
  "build": "mdx-deck build deck.mdx"
}
```

查看更多导出选项[导出文档](docs/exporting.md)

## CLI选项

```
-p --port     Dev server port
--no-open     Prevent from opening in default browser
-d --out-dir  Output directory for exporting
--no-html     Disable static HTML rendering
--out-file    Filename for screenshot or PDF export
--width       Width in pixels
--height      Height in pixels
--webpack     Path to webpack config file
```

## 文件

-   [主题化](docs/theming.md)
-   [内置主题](docs/themes.md)
-   [布局](docs/layouts.md)
-   [组件](docs/components.md)
-   [出口](docs/exporting.md)
-   [高级用法](docs/advanced.md)
-   [反应API](docs/react.md)

## 例子

-   [设计系统与反应][design-systems-react]通过[戴安娜山](https://mobile.twitter.com/broccolini)
-   [现在,将巴西带入云端][brazil-now]通过[吉列尔莫·劳赫](https://mobile.twitter.com/rauchg/)
-   [简化反应][simplify-react]通过[肯特C.多德斯](https://mobile.twitter.com/kentcdodds)
-   [我有99个问题,但GraphQL不是一个][99-problems]通过[萨拉维埃拉](https://mobile.twitter.com/NikkitaFTW)

* * *

### 有关

-   [MDX][]
-   [MDX-去][]
-   [ok-mdx][]
-   [Compositor x0][]
-   [风格组件-][]
-   [风格系统-][]
-   [场面][]

[MIT许可证](LICENSE.md)

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
