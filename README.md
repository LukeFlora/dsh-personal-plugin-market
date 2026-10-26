# 设计与 DSH 精选插件

这是一个供 DeepSeek Harness「插件 → 发现」添加的轻量市场索引。它从社区目录中只保留两个与你的项目连续性、提示词工作流直接相关的插件，避免把整个社区清单搬进来。你现有的专家 Bot 团队、协作能力和插件发现组件已经在用，因此首版不再收录重复的多智能体管理插件。

## 当前条目

| 插件 | 用途 | 使用前要知道 |
| --- | --- | --- |
| `@yolk_vat-y/dsh-project-memory` 0.6.5 | 跨会话保存项目任务、已读文件和经验 | 会在项目目录写入记忆数据；默认按模型实际读取的文件逐步建索引。 |
| `dsh-prompt-enhance` 0.2.1 | 优化提示词草稿并预览前后差异 | 会调用当前配置的模型改写草稿；需要用户确认才会替换原文。 |

## 发布并添加到 Harness

1. 市场索引已经发布在 [`LukeFlora/dsh-personal-plugin-market`](https://github.com/LukeFlora/dsh-personal-plugin-market)，GitHub Pages 从 `main` 分支根目录构建。
2. 在 Harness **插件 → 发现** 页面打开市场选择菜单，进入 **管理索引源…**，添加：

   `https://lukeflora.github.io/dsh-personal-plugin-market/index.json`

3. 添加后，Discover 页面只会列出这份索引中的两个插件。更新 `index.json` 并推送到 GitHub，即可更新市场内容。

索引按官方 format 1 编写。包名、版本与来源固定到已发布的 npm 版本；安装插件仍会运行第三方代码，安装前应查看确认框中的来源。该索引本身没有安装或启用插件。

## 当前边界

- 市场文件现已公开发布；访问索引需使用 GitHub Pages 的 HTTPS 地址。
- `publishTimestamp` 取对应版本发布日期的近似 UTC 时间，用于排序，不影响安装版本。
- 没有把截图中的验证回执与审计插件放进来：它们的公开兼容证据锁定在较旧的 DSH 版本/提交，先避免把可能不兼容的插件展示成可安装项。
- 此清单按当前使用场景做了小范围精选，不代表安全审计或官方背书。
