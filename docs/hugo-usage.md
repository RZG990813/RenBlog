# Hugo 使用指南

## 1. 分类（Categories）

分类用于对文章进行大组分类，每篇文章只能属于一个分类。

### Front Matter 中定义分类

```toml
---
title: "我的文章标题"
categories: ["技术"]  # 只能是单个分类
---
```

### 多级分类

```toml
---
categories: ["技术", "编程"]
---
```

### 分类的作用

- 自动生成分类页面：`yoursite.com/categories/技术/`
- 在文章列表中按分类显示

---

## 2. 标签（Tags）

标签用于对文章进行细粒度标记，一篇文章可以有多个标签。

### Front Matter 中定义标签

```toml
---
title: "我的文章标题"
tags: ["hugo", "静态网站", "教程"]  # 可以有多个标签
---
```

### 标签的作用

- 自动生成标签页面：`yoursite.com/tags/hugo/`
- 方便读者找到相关主题的文章

---

## 3. Front Matter 完整示例

```toml
---
title: "Hugo 教程"
author: "作者名"
date: 2024-01-13
lastmod: 2024-01-14
draft: false
featuredImage: "/images/hugo.jpg"
description: "这是一篇文章的简短描述"
categories: ["技术"]
tags: ["hugo", "静态网站", "入门教程"]
---

文章内容从这里开始...
```

### 常用字段说明

| 字段 | 说明 |
|------|------|
| `title` | 文章标题 |
| `author` | 作者名 |
| `date` | 发布日期 |
| `lastmod` | 最后修改日期 |
| `draft` | 是否为草稿（true/false） |
| `featuredImage` | 特色图片路径 |
| `description` | 文章描述（SEO用途） |
| `categories` | 分类（数组） |
| `tags` | 标签（数组） |

---

## 4. 文章内容结构

```
content/
├── posts/              # 博客文章目录
│   ├── my-first-post.md
│   ├── hugo-tutorial.md
│   └── ...
├── about.md            # 关于页面
└── contact.md          # 联系页面
```

### 创建新文章

使用 Hugo 命令创建：

```bash
hugo new posts/my-new-post.md
```

---

## 5. 常用 Shortcodes

### figure 图片

```markdown
{{</* figure src="/images/pic.jpg" caption="图片标题" alt="替代文本" */>}}
```

### ref 链接

```markdown
{{</* ref "posts/my-post.md" */>}}
```

### youtube 视频

```markdown
{{</* youtube "视频ID" */>}}
```

### tweet 推文

```markdown
{{</* tweet "推文ID" */>}}
```

---

## 6. 内部链接

```markdown
[链接文本](/posts/other-post/)      # 站内文章链接
[关于页面](/about/)                   # 站内页面链接
[外部链接](https://example.com)      # 外部链接
```

---

## 7. 代码块

```markdown
```go
func main() {
    fmt.Println("Hello, Hugo!")
}
```
```

---

## 8. 草稿文章

草稿文章不会在生产环境中显示：

```toml
---
draft: true
---
```

预览草稿：

```bash
hugo server -D
```

---

## 9. 目录结构说明

```
.
├── content/          # 内容目录
│   └── posts/        # 博客文章
├── layouts/          # 布局模板
├── static/           # 静态资源（图片、文件等）
├── themes/           # 主题
├── hugo.toml         # 配置文件
└── public/           # 生成的静态网站
```

---

## 10. 常用命令

```bash
hugo server          # 启动本地服务器
hugo server -D       # 包含草稿的预览
hugo                 # 生成静态网站
hugo env             # 查看 Hugo 环境信息
```

---

## 11. 总结

- **分类**：大组分类，每篇文章一个
- **标签**：细粒度标记，每篇文章多个
- **草稿**：`draft: true` 的文章不会发布
- **Shortcodes**：Hugo 特有的扩展语法
- **内容目录**：`content/` 下按需创建子目录