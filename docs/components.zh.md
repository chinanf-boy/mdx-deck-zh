
# 组件

mdx-deck包含一些内置组件,可帮助创建演示文稿.

## 头

使用`<Head />`用于在文档头中设置内容的组件.

```mdx
// example for twitter cards
import { Head } from 'mdx-deck'

<Head>
  <title>My Presentation</title>
  <meta name='twitter:card' content='summary_large_image' />
  <meta name='twitter:site' content='@jxnblk' />
  <meta name='twitter:title' content='My Presentation' />
  <meta name='twitter:description' content='A really great presentation' />
  <meta name='twitter:image' content='https://example.com/card.png' />
</Head>
```

## 图片

使用`<Image />`用于渲染全屏图像的组件(使用CSS`background-image`属性).

```mdx
import { Image } from 'mdx-deck'

<Image src='kitten.png' />
```

### 道具

-   `src`(字符串)图片网址
-   `size`(字符串)CSS background-size

## 出现

使用`<Appear />`组件使其子项在单个幻灯片中一次显示一个.使用向左和向右箭头键逐步浏览每个元素.

```mdx
import { Appear } from 'mdx-deck'

<ul>
  <Appear>
    <li>One</li>
    <li>Two</li>
    <li>Three</li>
  </Appear>
</ul>
```

## 演讲者备注

演讲者注意事项只能在演示者模式中显示,可以使用markdown语法或Notes组件添加到任何幻灯片.

````mdx
# Markdown speaker notes

```notes
These are only visible in presenter mode
```
````

```mdx
import { Notes } from 'mdx-deck'

# Slide Content

<Notes>
  Only visible in presenter mode
</Notes>
```

## 布局

mdx-deck包含一些用于常见幻灯片变化的内置布局.导出布局为`default`在幻灯片中包装内容.

### 倒置

从主题中反转前景色和背景色.

```mdx
import { Invert } from 'mdx-deck/layouts'

# Normal

---

export default Invert

# Inverted
```

### 分裂

创建一个水平布局,左边是第一个孩子,右边是所有其他孩子.

```mdx
import { Split } from 'mdx-deck/layouts'

export default Split

![](kitten.png)

## Meow
```

### SplitRight

与Split组件相同,但在右侧呈现第一个子组件.

```mdx
import { SplitRight } from 'mdx-deck/layouts'

export default SplitRight

![](kitten.png)

## Meow
```

### FullScreenCode

渲染围栏代码块全屏.

````mdx
import { FullScreenCode } from 'mdx-deck/layouts'

export default FullScreenCode

```jsx
<Button>Beep</Button>
```
````
