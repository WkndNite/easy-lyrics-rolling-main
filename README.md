# 简易音乐播放器

这是一个简单的音乐播放器项目，支持存放在 js 文件里的文件的解析和显示，随着音乐的播放高亮当前歌词。

## 项目特点

1. **实时歌词高亮**: 根据音频播放进度自动高亮当前歌词，为用户提供更好的体验。
2. **高效的 DOM 操作**: 使用文档碎片（Document Fragment）优化歌词元素的创建，减少页面重绘和回流，提高性能。
3. **自适应歌词滚动**: 根据当前播放时间动态计算歌词的滚动位置，使歌词在播放器中居中显示。

## 实现方法

1. **LRC 文件解析**: 解析 LRC 文件格式并处理时间和歌词的关系，确保歌词能在正确的时间显示。
2. **歌词滚动计算**: 需要精确计算歌词的高度和容器的高度，以实现平滑的滚动效果，避免歌词跳动。
3. **音频时间更新处理**: 在音频播放过程中，实时监听播放时间的变化并更新歌词显示状态，确保性能和用户体验。

## 项目结构

```plain text
.
├── .idea                   # 项目配置文件夹
│   ├── .gitignore
│   ├── LyricsRoll.iml
│   └── modules.xml
├── assets                  # 静态资源文件夹
│   ├── favicon.ico         # 网站图标
│   └── music.mp3           # 音频文件
├── css                     # 样式文件夹
│   └── index.css           # 页面样式
├── js                      # JavaScript 文件夹
│   ├── data.js             # LRC 数据存储脚本
│   └── index.js            # 主要功能脚本
├── .gitignore              # git 忽略文件
├── index.html              # 主 HTML 页面
└── README.md               # 项目说明文档
```

### 核心功能

-   `parseTime(timeStr)`: 将时间字符串转换为秒数。
-   `parseLrc()`: 解析 LRC 文件内容并返回时间和歌词的数组。
-   `findHighlightIndex()`: 根据当前音频时间找到高亮歌词的索引。
-   `getDOMs()`: 获取音频播放器和歌词容器的 DOM 元素。
-   `createElementEfficiency()`: 高效创建歌词列表项并添加到 DOM 中。
-   `setOffset()`: 设置歌词的滚动偏移量，并高亮当前歌词。

### 事件监听

在 DOM 完全加载后，初始化播放器并为音频的 `timeupdate` 事件添加监听器，以实时更新歌词显示。

## 贡献

欢迎提交问题、建议和贡献代码，帮助我们改进这个项目！请遵循 [贡献指南](CONTRIBUTING.md)。

## License

本项目采用 MIT 许可证，详情请参见 [LICENSE](LICENSE) 文件。
