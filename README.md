# 武汉大学计算机学院课程设计报告，实验报告 Typst 模板

本项目依据《武汉大学计算机学院课程设计报告书写规范（修订版）》编写，实现了封皮、声明页、目录、正文、图表公式、参考文献及教师评语页的复刻。

相比于 Word，使用 Typst 将获得：

- **极速编译**：所见即所得，告别 Word 排版崩溃。
- **完美公式**：像 LaTeX 一样优雅地书写数学公式。
- **模块化**：样式与内容分离，专注于写作本身。
- **精准合规**：已预设好字体大小、行间距（23磅）、页边距等死板要求。

## 如何使用

### 1. 环境准备

- **VS Code (推荐)**: 安装 [Tinymist](https://marketplace.visualstudio.com/items?itemName=myriad-dreamin.tinymist) 插件，它集成了语法高亮和实时预览。
- **命令行**: 参考 [Typst 官方文档](https://github.com/typst/typst) 安装 CLI 工具。

**字体警告**： 模板依赖系统的 `SimSun` (宋体)、`SimHei` (黑体) 和 `Times New Roman`。

- **Windows**: 开箱即用。
- **macOS / Linux**: 请确保安装了上述字体，或者修改 `template.typ` 中的字体定义。

### 2. 获取模板

```bash
git clone https://github.com/raitocc/whu-cs-report-typst.git
cd whu-cs-report-typst
```

### 3. 开始写作

打开 `main.typ` 文件，这是主入口。

1. **修改个人信息**： 在 `project` 函数中填入你的信息：

   ```
   #show: project.with(
     title: "你的报告题目",
     major: "软件工程",
     course: "课程名称",
     student-name: "张三",
     // ...
   )
   ```

2. **撰写正文**： Typst 的语法非常简洁，类似 Markdown：

   ```
   = 一级标题 (自动黑体小二)
   == 二级标题 (自动黑体四号)
   
   这是正文段落，自动首行缩进两字符。*这是加粗文字*。
   
   // 插入图片
   #figure(
     image("assets/pic.png", width: 80%),
     caption: [系统架构图]
   )
   
   // 插入公式
   $y = k x + b$
   
   // 引用参考文献
   根据文献 #cite(<lecun2015>) 所述...
   ```

3. **导出 PDF**： 如果使用 VS Code 插件，点击右上角的 "Export PDF" 按钮，或者保存时自动导出。 命令行方式：

   ```
   typst compile main.typ
   ```

