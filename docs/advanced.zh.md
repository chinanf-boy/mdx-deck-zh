
# 高级用法

## 自定义MDX组件

mdx-deck包含MDX的默认组件,但提供自定义组件[MDXProvider][],添加一个`components`反对`theme`.

```js
// example theme
import { theme } from 'mdx-deck/themes'
import Heading from './Heading'

export default {
  ...theme,
  components: {
    h1: Heading
  }
}
```

见[MDX][]docs for more或者看看[默认的组件集](../src/components.js)作为参考.

## Custom Provider组件

可以将自定义提供程序组件添加到主题以包装整个应用程序.这对于在React中添加自定义上下文提供程序很有用.

```js
// example theme.js
import { theme } from 'mdx-deck/themes'
import Provider from './Provider'

export default {
  ...theme,
  font: 'Georgia, serif',
  Provider
}
```

自定义提供程序组件将接收应用程序的状态作为props,可用于显示自定义页码或向UI添加其他元素.

#### 道具

-   `index`:(数字)当前幻灯片索引
-   `length`:(数字)幻灯片数组的长度
-   `mode`:(字符串)当前模式(其中之一)`'NORMAL'`,`'PRESENTER'`, 要么`'OVERVIEW'`)
-   `notes`:(对象)自定义[演讲者笔记](#speaker-notes)适用于所有幻灯片
-   `step`:(数字)出现组件中的当前可见步骤

## 合并多个mdx文件

与官方不同`@mdx-js/loader`,`mdx-deck/loader`导出一组组件而不是一组件.如果文件大小难以管理,则可以将多个MDX文件合并为单个演示文稿.

首先创建一对`.mdx`像任何其他mdx-deck文件一样的文件`---`分开不同的幻灯片.

```mdx
# one.mdx

---

This is the first file
```

```mdx
# two.mdx

---

This is the second file
```

接下来,创建一个`.js`文件导入并合并两者`.mdx`文件.

```js
// deck.js
import one from './one.mdx'
import two from './two.mdx'

export default [
  ...one,
  ...two
]
```

然后,将mdx-deck CLI注释指向您的`package.json`到了`deck.js`文件.

```json
"scripts": {
  "start": "mdx-deck deck.js"
}
```

## 自定义webpack配置

Webpack配置文件命名`webpack.config.js`将使用自动与内置配置合并[的WebPack合并](https://github.com/survivejs/webpack-merge).要使用自定义文件名,请将文件路径传递给`--webpack`旗.

```js
// webpack.config.js example
module.exports = {
  module: {
    rules: [
      { 
        test: /\.svg$/, 
        use: [
          { loader: 'babel-loader' },
          { loader: 'react-svg-loader' }
        ]
      }
    ]
  }
}
```

**小心**:覆盖加载器时`mdx`文件,请确保包含默认加载器`mdx-deck/loader`.

## 自定义构建设置

核心mdx-deck组件也可用于任何React应用程序,例如[CREATE-反应应用内-][]要么[next.js][].

见[反应API](react.md)docs for more.

[mdx]: https://github.com/mdx-js/mdx

[mdxprovider]: https://github.com/mdx-js/mdx#mdxprovider

[create-react-app]: https://github.com/facebook/create-react-app

[next.js]: https://github.com/zeit/next.js/
