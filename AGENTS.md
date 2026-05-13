# 醍醐堂記 Hugo Blog — AGENTS.md

本文件接管并整理原 `../CLAUDE.md` 中与博客主站相关的项目知识，作为当前仓库 `tihu-hugo-blog/` 的统一协作文档。

## 项目定位

- 项目名：`醍醐堂記_TihuBlogs`
- 仓库路径：`/Users/quintinwang/Documents/HugoBlogs/tihu-hugo-blog`
- 线上地址：`https://tihu.github.io/tihu-hugo-blog/`
- 技术栈：Hugo + PaperMod
- 主题语言：中文主站 + 英文子站（`/en/`）

## Git 与部署

- 当前主仓库分支：`main`
- 远程仓库：`origin = git@github.com:tihu/tihu-hugo-blog.git`
- GitHub Pages 通过 `.github/workflows/deploy.yml` 自动部署
- 部署触发方式：`git push origin main`
- Git 已经配置完成，正常维护时不要改 remote、不要重建仓库配置

### 一句话更新线上博客

```bash
git add -A && git commit -m "更新博客" && git push origin main
```

说明：

- 不需要手动提交 `public/`
- 不需要手动执行部署脚本
- push 到 `main` 后，GitHub Actions 会自动用 Hugo 构建并发布

## 主题与 submodule 规则

- 主题目录：`themes/PaperMod`
- 它是 git submodule，不要在 `themes/PaperMod/` 目录里直接做普通内容提交
- 如果只是站点定制，优先改这些位置：
  - `layouts/`
  - `assets/css/extended/`
  - `static/`
  - `content/`
  - `content.en/`
- 如确实要升级主题，应在仓库根目录更新 submodule 指针，而不是把主题当普通目录乱改

## 本地工作流

常用命令：

```bash
hugo server
```

```bash
hugo --minify
```

约定：

- 本地预览优先用 `hugo server`
- 生产构建可用 `hugo --minify`
- CI 当前在 GitHub Actions 中使用 Hugo `0.158.0`
- `public/`、`resources/` 已在 `.gitignore` 中，默认不纳入版本控制

## 关键目录

```text
tihu-hugo-blog/
├── content/                    # 中文内容
├── content.en/                 # 英文内容
├── layouts/                    # 自定义布局
├── assets/css/extended/        # 自定义样式覆盖
├── static/                     # 静态资源
├── themes/PaperMod/            # 主题 submodule
├── .github/workflows/          # GitHub Pages 自动部署
└── hugo.toml                   # 主配置
```

当前站点里比较关键的定制文件：

- `layouts/index.html`
- `layouts/_default/list.html`
- `layouts/_default/single.html`
- `layouts/partials/sidebar.html`
- `layouts/partials/lang_switch.html`
- `layouts/partials/extend_head.html`
- `assets/css/extended/blank.css`

## Hugo 配置要点

- `baseURL = "https://tihu.github.io/tihu-hugo-blog/"`
- `defaultContentLanguage = "zh"`
- 英文站放在 `/en/`
- `paginate = 15`
- `canonifyURLs = true`
- 首页输出：HTML / RSS / JSON

## 内容维护规则

### 文件命名

- 文章文件名统一采用 `YYYY-MM-DD-keyword.md`
- `keyword` 优先短英文；没有合适英文词时可用简短拼音
- 文件名主要服务本地维护与 git 管理，不承担完整标题功能
- 历史文章如改过文件名，为避免旧 URL 失效，应在 front matter 保留对应 `slug`

### 分类与标签

规则：每篇文章都要填写 `categories` 和 `tags`，不能留空。

固定分类共 5 个：

- `四时随笔`
- `焚字塔`
- `读书笔记`
- `赛博生活`
- `播客手账`

常用标签共 9 个：

- `醍醐堂记`
- `虚构作品`
- `非虚构作品`
- `译异录`
- `六州杂记`
- `毗卢遮那`
- `瞳者菲林`
- `诸仙众神`
- `赛博八荒`

常见对应关系：

- `四时随笔` + `六州杂记` 或 `赛博八荒`
- `焚字塔` + `虚构作品` + `醍醐堂记` 或 `译异录`
- `焚字塔` + `非虚构作品` + `诸仙众神`
- `播客手账` + `六州杂记` 或 `诸仙众神`
- `读书笔记` + `六州杂记`

### 双语范围

- 中文主站仍是主体
- 英文站当前只覆盖部分分类，现阶段实际范围是 `焚字塔`
- `四时随笔`、`读书笔记`、`播客手账` 暂不做英文版
- 当新增文章属于英文覆盖范围内的分类时，需要同步新增英文译文页面
- 中英文页面映射通过 front matter 中的 `translationKey` 维护，中文页与英文页必须使用同一个值
- 英文译文通常放在 `content.en/posts/<year>/` 下，中文原文在 `content/posts/<year>/` 下
- 如果某篇中文文章已有 `translationKey`，则默认它应当存在或计划存在对应英文页，不要随意删改这个键
- 与英文翻译相关的整理文件：
  - `FENZITA_TRANSLATION_INVENTORY.md`
  - `FENZITA_TRANSLATION_TERMS.md`
  - `FENZITA_SAMPLE_BATCH.md`

双语维护的最小检查项：

- 中文原文 front matter 中有 `translationKey`
- 英文译文 front matter 中使用相同的 `translationKey`
- 英文页放入正确年份目录
- 英文页标题、分类、标签按英文站当前约定填写

### 图片规则

- 图片放在 `static/images/`
- Markdown 中使用 `/images/xxx.jpg`
- 之前开启 `canonifyURLs = true`，就是为了解决子路径图片 404

## 已确认的站点特征

- 左侧栏是全站共享结构，已抽成 partial
- 导航当前以「首页 / 归档」为主
- 字体使用 `LXGW WenKai`，通过 CDN 引入
- 中文与英文页都已适配当前双栏布局
- 明暗模式按钮、语言切换、侧栏外链都做过定制，不宜随手回退

## 协作注意事项

- 做博客更新时，优先保持现有视觉和信息结构稳定
- 改布局时先检查 `layouts/` 与 `assets/css/extended/`，不要直接改主题内部文件
- 若仓库根目录状态干净，可直接提交并 push
- 若 `themes/PaperMod` 显示变更，先确认是不是 submodule 指针变化，不要误把主题内部改动当普通内容处理

## 历史背景摘要

- 2026-04 已完成全站分类与标签整理
- 站点已改为双栏布局
- GitHub Pages 自动部署链路已跑通
- `public/` 已移出版本控制
- 英文站骨架已建立并已有部分译文

## 当前接管说明

- 现在由 Codex 接管该项目的协作记录与执行
- 旧 `CLAUDE.md` 仍可作为历史参考，但以后以本文件为准
