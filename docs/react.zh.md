
# 反应API

核心mdx-deck组件也可用于任何React应用程序,例如[CREATE-反应应用内-][]要么[next.js][].

### Webpack Loader

mdx-deck使用自定义webpack加载程序将MDX文件拆分为幻灯片数组.使用此加载程序在webpack应用程序中导入mdx文件.

```js
// example webpack.config.js
module.exports = {
  module: {
    rules: [
      {
        test: /\.mdx$/,
        ignore: /node_modules/,
        use: [
          'babel-loader',
          'mdx-deck/loader'
        ]
      }
    ]
  }
}
```

### SlideDeck组件

```js
import React from 'react'
import { SlideDeck } from 'mdx-deck'
import slides from './deck.mdx'
import theme from './theme'

export default () =>
  <SlideDeck
    slides={slides}
    theme={theme}
    width='100vw'
    height='100vh'
  />
```

查看可供使用的其他组件的来源.

[create-react-app]: https://github.com/facebook/create-react-app

[next.js]: https://github.com/zeit/next.js/
