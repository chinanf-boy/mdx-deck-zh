
# 布局

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

## 内置布局

mdx-deck包含一些用于常见幻灯片变化的内置布局.

见[组件文档](components.md#layouts)更多.
