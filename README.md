pyenv: cannot rehash: /Users/design/.pyenv/shims isn't writable
# 设计与 DSH 精选插件

这是一个供 DeepSeek Harness「插件 → 发现」添加的轻量市场索引。它从社区目录中只保留两个与你的项目连续性、提示词工作流直接相关的插件，避免把整个社区清单搬进来。你现有的专家 Bot 团队、协作能力和插件发现组件已经在用，因此首版不再收录重复的多智能体管理插件。

## 当前条目

| 插件 | 用途 | 使用前要知道 |
| --- | --- | --- |
| `@yolk_vat-y/dsh-project-memory` 0.6.5 | 跨会话保存项目任务、已读文件和经验 | 会在项目目录写入记忆数据；默认按模型实际读取的文件逐步建索引。 |
| `dsh-prompt-enhance` 0.2.1 | 优化提示词草稿并预览前后差异 | 会调用当前配置的模型改写草稿；需要用户确认才会替换原文。 |

## 发布并添加到 Harness

1. 把本目录放进一个 GitHub 仓库，例如 `dsh-personal-plugin-market`。
2. 在 GitHub 仓库的 **Settings → Pages** 中，从 `main` 分支的根目录发布。
3. 等 Pages 发布后，在 Harness **插件 → 发现** 页面打开市场选择菜单，进入 **管理索引源…**，添加：

   `https://<你的用户名>.github.io/dsh-personal-plugin-market/index.json`

4. 添加后，Discover 页面只会列出这份索引中的两个插件。更新 `index.json` 并推送到 GitHub，即可更新市场内容。

索引按官方 format 1 编写。包名、版本与来源固定到已发布的 npm 版本；安装插件仍会运行第三方代码，安装前应查看确认框中的来源。该索引本身没有安装或启用插件。

## 当前边界

- 这是本地准备好的索引，尚未发布到公网；Discover 的索引管理需要可从 Harness 访问的 HTTPS 地址。
- `publishTimestamp` 取对应版本发布日期的近似 UTC 时间，用于排序，不影响安装版本。
- 没有把截图中的验证回执与审计插件放进来：它们的公开兼容证据锁定在较旧的 DSH 版本/提交，先避免把可能不兼容的插件展示成可安装项。
- 此清单按当前使用场景做了小范围精选，不代表安全审计或官方背书。
