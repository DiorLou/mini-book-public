# Mini Book

这个公开仓库维护三本相互独立的 MyST 笔记，并为每一本生成网页和 PDF。

| 内容 | 源目录 | 网页路径 | PDF |
| --- | --- | --- | --- |
| American intonation | `american intonation/` | `/american-intonation/` | `american-intonation.pdf` |
| 记单词 | `vocabulary/` | `/vocabulary/` | `vocabulary-notes.pdf` |
| CS61A: Structure and Interpretation of Computer Programs | `cs61a/` | `/cs61a/` | `cs61a-notes.pdf` |

## 使用 Codex 整理笔记

仓库在 `.agents/skills/` 中提供三个 Codex Skill。使用 Codex 打开本仓库后，可以通过自然语言触发：

- `organize-minibook-notes`：把当前问答重写成可独立阅读的 MyST 笔记，选择合适的书籍与章节，并更新 `toc.yml`。
- `collect-video-learning-notes`：连续收集视频字幕截图和个人理解；收到“我发完了”等结束信号后，再统一去重、梳理并写入书籍。
- `record-english-vocabulary`：把英语单词的音标、语境义、原始例句和必要语法按日期写入《记单词》。

示例指令：

```text
把刚才关于英语语调的问答整理成笔记，位置你判断。
开始收集这段视频的学习笔记，我会连续发送截图，等我说发完了再整理。
这个句子里的 composure 是什么意思？
```

Skill 会直接修改当前仓库中的 Markdown 和目录文件。提交前请先查看 Git diff，确认笔记内容与归档位置符合预期。

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

推送到 `main` 分支后，GitHub Actions 会构建三本书籍，生成首页并部署到 GitHub Pages。
