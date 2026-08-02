# 手机端维护博客教程（水车生活Share）

本教程说明如何用手机（或任何电脑浏览器）维护你的 Hexo 博客：
写新文章、修改公告、修改关于页等。**全程不需要电脑装任何软件，手机上操作即可。**

---

## 一、前提

1. 手机安装 **GitHub App**（App Store / 应用市场搜索 "GitHub"），或直接用手机浏览器打开 https://github.com 并登录。
2. 你的博客仓库：`Shi369/Shi369.github.io`（公开仓库，登录后即可操作）。
3. 发布原理：你在手机上修改 markdown 文件并提交（Commit）→ GitHub 自动构建 → 1~2 分钟后博客更新。你什么都不用装。

---

## 二、写新文章（最重要的操作）

### 方法 A：GitHub App（推荐）

1. 打开 GitHub App，进入仓库 `Shi369/Shi369.github.io`。
2. 进入文件夹：`source` → `_posts`。
3. 点击右上角"＋"（新建文件）。
4. 文件名填文章标题，例如：`我的新文章.md`（**必须以 .md 结尾**）。
5. 内容按下面模板填写：

```markdown
---
title: 我的新文章
date: 2026-08-02 15:00:00
tags:
  - 随笔
categories:
  - 生活
---

正文从这里开始，直接写字就行。

## 二级标题

- 列表项一
- 列表项二

**加粗**、*斜体*、`代码` 都支持。
```

6. 点 **Commit changes**（提交更改），会自动触发部署。
7. 等 1~2 分钟，刷新 https://www.watech.top/ 就能看到新文章。

### 方法 B：手机浏览器

打开 https://github.com/Shi369/Shi369.github.io/tree/main/source/_posts
→ 点右上角 "Add file" → "Create new file" → 同上填写。

---

## 三、修改公告（侧边栏那条）

1. 进入仓库根目录，打开文件 `_config.butterfly.yml`。
2. 按 Ctrl+F（手机浏览器点菜单→查找）搜索 `card_announcement`。
3. 修改 `content:` 后面引号里的文字即可，支持简单 HTML：
   - `<br>` = 换行
   - `<b>文字</b>` = 加粗
   - `<a href="网址">文字</a>` = 链接
   - `<center>文字</center>` = 居中
4. 保存并 Commit。

示例：
```yaml
card_announcement:
  enable: true
  content: |
    欢迎来到我的小站！<br>
    <b>本站公告：</b>有事请发邮件
```

---

## 四、修改关于页

1. 进入 `source/about/` 文件夹。
2. 打开 `index.md`，修改正文部分（`# About` 下面的内容），支持 Markdown。
3. 保存并 Commit。

---

## 五、修改友链页

1. 进入 `source/link/` 文件夹。
2. 打开 `index.md`，里面是按分组排列的友链卡片 HTML。
3. 要加一个友链，复制一个 `<div class="flink-list-item">...</div>` 整段，改里面的链接、名字、头像、描述即可。
4. 保存并 Commit。

---

## 六、文章里放图片

### 方式 1：上传到博客仓库（推荐，稳定）

1. 进入仓库 `source/images/` 文件夹。
2. 点 "Add file" → "Upload files"，把手机里的图片传上去（可以传进 `pages` 子文件夹）。
3. 记住上传后的路径，例如图片叫 `photo1.png` 传到了 `source/images/pages/`。
4. 文章里引用：`![](/images/pages/photo1.png)`

### 方式 2：用免费图床

打开 https://sm.ms 等图床网站上传图片，得到外链 URL，文章里写 `![](图片URL)`。

---

## 七、修改其他页面 / 配置

| 想改什么 | 改哪个文件 |
|---------|-----------|
| 公告 | 根目录 `_config.butterfly.yml` 里的 `card_announcement` |
| 关于页 | `source/about/index.md` |
| 友链页 | `source/link/index.md` |
| 站点标题/副标题 | 根目录 `_config.yml` 里的 `title` / `subtitle` |
| 头像/背景图 | `_config.butterfly.yml` 里的 `avatar` / `default_top_img` |
| 删除文章 | 进入 `source/_posts/`，打开文章点删除，再 Commit |

---

## 八、常见问题

**Q：提交了但网站没变化？**
A：等 1~2 分钟。如果超过 5 分钟，去 https://github.com/Shi369/Shi369.github.io/actions 看 Actions 是否失败，把失败信息发给我。

**Q：文章标题有中文字符/特殊符号？**
A：文件名尽量简单（如 `my-post.md`），标题在 front-matter 的 `title:` 里写中文即可。

**Q：`date` 怎么写？**
A：格式 `2026-08-02 15:00:00`（年-月-日 时:分:秒）。不填也没关系，会用提交时间。

**Q：想写的文章还没写完，不想发布？**
A：把 `date:` 改成未来时间（如 2099-01-01），或者先不发，写完再提交。

---

## 九、常用文章模板（复制即用）

```markdown
---
title: 文章标题
date: 2026-08-02 15:00:00
tags:
  - 标签一
categories:
  - 分类一
---

正文……

## 小标题

- 要点一
- 要点二

![图片说明](/images/pages/图片名.png)
```

---

本教程文件位于博客仓库根目录，随时可在 https://github.com/Shi369/Shi369.github.io 查看。
