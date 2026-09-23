# Mini Book

这个公开仓库维护四本相互独立的 MyST 笔记，并为每一本生成网页和 PDF。

| 内容 | 源目录 | 网页路径 | PDF |
| --- | --- | --- | --- |
| 计算机与深度学习 | `deep learning/` | `/computer/` | `computer-notes.pdf` |
| 金融投资 | `finance/` | `/finance/` | `finance-notes.pdf` |
| American intonation | `american intonation/` | `/american-intonation/` | `american-intonation.pdf` |
| 记单词 | `vocabulary/` | `/vocabulary/` | `vocabulary-notes.pdf` |

## 本地构建

安装 Node.js、MyST 和 Typst 后，在仓库根目录执行：

```powershell
npm install -g mystmd
./scripts/build-all.ps1
```

每个项目的网页和 PDF 会生成在对应目录的 `_build/` 中。

增量构建发生变化的书籍、启动本地服务器并打开浏览器：

```powershell
./scripts/preview.cmd
```

## 发布

推送到 `main` 分支后，GitHub Actions 会构建四本书籍，生成首页并部署到 GitHub Pages。
