
# 出口

## 静态捆绑

要使用JS包将您的套牌导出为静态HTML页面,请添加一个`build`脚本给你`package.json`文件.

```json
"scripts": {
  "build": "mdx-deck build deck.mdx"
}
```

## PDF导出

可以使用CLI将演示文稿导出为PDF.这适用于任何无法预料的技术难题的备份选项.

```json
"script": {
  "pdf": "mdx-deck pdf deck.mdx"
}
```

## 截图

可以使用导出第一张幻灯片的PNG图像`screenshot`命令.这对于为Twitter,Facebook或Slack创建开放图形图像很有用.

```json
"script": {
  "screenshot": "mdx-deck screenshot deck.mdx"
}
```

### OG图片

要将图像用作打开的图形图像,请使用[头](components.md#Head)用于添加元标记的组件.请注意,元标记应指向完整的URL,包括架构和域名.

```mdx
import { Head } from 'mdx-deck'

<Head>
  <meta name='og:image' content='https://example.com/card.png' />
</Head>
```
