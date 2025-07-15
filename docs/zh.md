该主题是作为 Astro 的集成来安装的, 通过这种方式可以让 git 提交历史更加清晰, 当主题发布新版本时, 也能更方便地对主题进行升级.

如果你还没有现成的 Astro 项目, 那你可以参考 [官方文档](https://docs.astro.build/zh-cn/install-and-setup/) 进行项目初始化.

## 用法

### 安装依赖

```sh
pnpm add https://github.com/miaobuao/astro-theme-meo-minimalism.git
```

### 配置 astro

更新你的 `astro.config.mjs`:

```ts
// astro.config.mjs
import theme from 'astro-theme-meo-minimalism'
import { defineConfig } from 'astro/config'

export default defineConfig({
	site: 'https://example.com',
	integrations: [
		theme({
			site: {
				title: `Example Blog`,
				description: 'Here is Example Blog!',
				locale: 'zh-CN',
				url: 'https://example.com',
			},
			author: {
				name: 'Example',
				email: 'user@example.com',
				signature: 'To Be A Geek :)',
				avatar: {
					url: 'https://avatars.githubusercontent.com/u/62047803?v=4',
					alt: 'Meo',
				},
			},
			pages: {
				aboutMe: '/about',
			},
		}),
		// ... other integrations
	],
})
```

### 自定义 "关于我" 页面

你可以在 `src/pages/about.mdx` 里写关于你自己的信息, 为了保持统一的设计风格, 可以使用我们提供的布局 (当然你也可以自己写一个 astro 页面):

```mdx
---
layout: 'astro-theme-meo-minimalism/layouts/HomeLayout.astro'
---

import 'astro-theme-meo-minimalism/styles/post.scss'
import Footer from 'astro-theme-meo-minimalism/components/Footer.astro'

<main class="flex justify-center items-center">
<article class="prose dark:prose-invert p-4">

# 关于我

[欢迎你来到我的博客](https://yangqiuyi.com)

</article>
</main>

<Footer class="pb-4" />
```
