
# 主题化

mdx-deck使用[风格组件-][]用于造型,几乎可以使演示文稿的任何部分成为主题.

## 内置主题

mdx-deck包含几个内置主题,用于更改演示文稿的外观和风格.出口`theme`从您的MDX文件中启用主题.

```mdx
export { dark as theme } from 'mdx-deck/themes'

# Dark Theme
```

查看[主题列表](themes.md).

## 自定义主题

可以通过导出提供自定义主题`theme`来自MDX文件.

```mdx
export { default as theme } from './theme'

# Hello
```

主题应该是一个对象,其中包含各个组件的字体,颜色和CSS字段.建议所有自定义主题都将默认主题扩展为基础.

```js
// Example theme.js
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

### 谷歌字体

要使用webfonts,mdx-deck将尝试添加`<link>`Google字体中任何字体的标签.要从其他来源加载Webfonts,请使用自定义[提供者组件](advanced.md#custom-provider-component)添加自定义`<link>`标签.

### 语法突出显示

默认情况下,受防护的代码块不包含任何语法突出显示.可以通过提供a来启用隔离代码块中的语法突出显示`prism`主题中的样式对象.语法高亮是使用[反应 - 句法 - 荧光笔][]和[PrismJS][].创建一个`theme.js`文件并通过它导出`MDX`文件.

```js
export { default as theme } from './theme'
//...
```

```js
// example theme.js
import { future } from 'mdx-deck/themes'
import okaidia from 'react-syntax-highlighter/styles/prism/okaidia'

export default {
  ...future,
  prism: {
    style: okaidia
  }
}
```

默认情况下,仅启用JavaScript和JSX以进行语法突出显示,以使捆绑包大小保持最小.要启用其他语言,请添加`languages`反对`prism`主题中的对象.

```js
// example theme.js
import { future } from 'mdx-deck/themes'
import okaidia from 'react-syntax-highlighter/styles/prism/okaidia'
import prismRuby from 'react-syntax-highlighter/languages/prism/ruby'

export default {
  ...future,
  prism: {
    style: okaidia,
    languages: {
      ruby: prismRuby
    }
  }
}
```

有关可用语法样式和语言的列表,请参阅:

-   [棱镜语言](https://github.com/conorhastings/react-syntax-highlighter/blob/master/AVAILABLE_LANGUAGES_PRISM.MD)
-   [棱镜款式](https://github.com/conorhastings/react-syntax-highlighter/blob/master/AVAILABLE_STYLES_PRISM.MD)

[prismjs]: https://github.com/PrismJS/prism

[react-syntax-highlighter]: https://github.com/conorhastings/react-syntax-highlighter

### 幻灯片切换

可以使用自定义主题自定义幻灯片转换计时功能和持续时间.

```js
// example theme
import theme from 'mdx-deck/themes'

export default {
  ...theme,
  transitionTimingFunction: 'linear',
  transitionDuration: '.1s'
}
```

### 造型元素

每个元素都可以使用主题进行样式设置.向主题添加样式对象(或字符串)以定位特定元素.

```js
// example theme
import theme from 'mdx-deck/themes'

export default {
  ...theme,
  h1: {
    textTransform: 'uppercase',
    letterSpacing: '0.1em'
  },
  blockquote: {
    fontStyle: 'italic'
  }
}
```

见[参考](#reference)下面是元素键的完整列表.

## 参考

以下键可用于主题:

-   `font`:基本字体系列
-   `weights`:主字体的字体粗细数组
-   `monospace`:字体系列`<pre>`和`<code>`
-   `fontSizes`:从最小到最大的字体大小数组
-   `colors`:用于MDX组件的颜色对象
    -   `text`:根前景色
    -   `background`:根背景色
    -   `link`
    -   `heading`
    -   `blockquote`
    -   `pre`
    -   `preBackground`
    -   `code`
    -   `codeBackground`
-   `transitionTimingFunction`:幻灯片切换的计时功能值
-   `transitionDuration`:幻灯片切换的持续时间值.设置`0`禁用转换
-   `css`:根CSS对象
-   `heading`:所有标题的CSS
-   `h1`:CSS for`<h1>`
-   `h2`:CSS for`<h2>`
-   `h3`:CSS for`<h3>`
-   `h4`:CSS for`<h4>`
-   `h5`:CSS for`<h5>`
-   `h6`:CSS for`<h6>`
-   `paragraph`:CSS for`<p>`
-   `link`:CSS for`<a>`
-   `ul`:CSS for`<ul>`
-   `ol`:CSS for`<ol>`
-   `li`:CSS for`<li>`
-   `img`:CSS for`<img>`
-   `blockquote`:CSS for`<blockquote>`
-   `table`:CSS for`<table>`
-   `components`:MDX组件的对象以呈现markdown
-   `Provider`:用于包装整个应用程序的组件

## 高级用法

有关更高级的自定义,请参阅[高级用法](advanced.md)文档.

[styled-components]: https://github.com/styled-components/styled-components

[mdx]: https://github.com/mdx-js/mdx
