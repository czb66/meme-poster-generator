# Meme Poster Generator

一个面向 Codex 的中文互联网梗图与热点文字海报生成技能。它会分析本地参考图、筛选适合排版的中文话题，并用图像生成工具批量制作竖版文字海报。

## 安装

在 Codex 中打开技能安装器，并让它从 GitHub 安装：

```text
Install the skill from https://github.com/czb66/meme-poster-generator
```

也可以下载仓库后，把整个目录复制到 `~/.codex/skills/meme-poster-generator`。

## 使用示例

```text
使用 $meme-poster-generator，参考 asset 文件夹里的图片，查找 10 个近期中文网络热梗，并把海报保存到 out 文件夹。
```

运行前请在项目中准备 `asset/` 参考图目录。生成结果默认写入 `out/`。

## 许可

MIT License
