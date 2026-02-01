# Whisper48

[English](https://github.com/ifeimi/Whisper48/blob/main/README.md) | 简体中文

## 什么是 Whisper48？

**Whisper48** 是一个易于使用的工具，可以从视频和音频文件中自动生成**精确的字幕**。它使用先进的 AI 模型来：

- ✅ 自动将语音转换为文本
- ✅ 生成精确的字级时间戳（每个词语说出的时间）
- ✅ 支持多种语言（日语、中文、英语、法语、德语、西班牙语、意大利语、葡萄牙语、俄语等）
- ✅ 完全在云端运行（无需安装！）

**适合以下人群：** 视频制作者、翻译者、内容创作者、播客编辑，以及任何需要转录音频而不想做繁重手工工作的人。

---

## 🚀 快速入门指南（无需编程知识！）

### 选项 1：云端使用（推荐初学者）

使用 **Google Colab** 是最简单的方式 - 这是一个免费的云服务，为您运行软件。无需安装！

#### 逐步说明：

**1. 准备您的文件**
   - 准备好您的音频或视频文件（MP3、WAV、MP4、MKV 等）
   - 将其上传到您的 **Google 云盘**（如果没有账户，创建一个免费的 Google 账户）
   - 将文件放在 Google 云盘的任何文件夹中 - 笔记本会帮您找到它

**2. 打开笔记本**
   - 点击此链接：[**WhisperX48 on Google Colab**](https://colab.research.google.com/github/ifeimi/Whisper48/blob/main/WhisperX48.ipynb)
   - Google 会在浏览器中打开笔记本

**3. 配置 GPU（重要！）**
   - 在页面顶部，点击 `Runtime`（运行时） → `Change runtime type`（更改运行时类型）
   - 选择 **GPU** 作为硬件加速器
   - 点击 `Save`（保存）
   - 这样您就可以获得免费的计算能力来更快地处理文件

**4. 按顺序运行每个步骤**
   - 每个单元格（代码块）都有**中文和英文**的清晰说明
   - 点击 ▶ 按钮（或按 Ctrl+Enter）逐个运行每个单元格
   - 等待完成后再进行下一个
   - 笔记本会引导您完成：
     1. 连接到 Google 云盘
     2. 安装必需的软件
     3. 选择您的媒体文件
     4. 配置设置（语言、模型大小等）
     5. 处理并下载您的字幕

**5. 下载您的字幕**
   - 处理完成后，字幕文件（`.srt` 格式）将自动下载
   - 在任何视频编辑器中使用此文件（Adobe Premiere、DaVinci Resolve、CapCut 等）

#### 获得最佳结果的提示：
- **音频质量**：音频越清晰 = 效果越好。如果可能，使用原始音轨而不是压缩版本
- **模型大小**：选择 `large-v2` 或 `large-v3` 以获得最佳精度。更大的模型耗时更长但更准确
- **语言选择**：选择正确的内容语言以获得更好的精度
- **分块大小**：除非您知道自己在做什么，否则保持默认的 5 秒

#### 常见问题排查：

| 问题 | 解决方案 |
|-------|----------|
| "GPU not found"（未找到 GPU）错误 | 转到 `Runtime`（运行时）→ `Change runtime type`（更改运行时类型），确保选择了 GPU |
| 运行非常缓慢 | GPU 内存问题 - 在高级设置中减少 `batch_size`，或使用更小的模型 |
| 字幕时间不准确 | 尝试使用 `large-v3` 模型而不是 `large-v2`，或检查音频质量 |
| 浏览器中未显示文件 | 再次运行文件浏览器单元格（步骤 1.3）刷新文件列表 |

---

### 选项 2：在您的计算机上本地运行

**要求：**
- 具有高级技术知识
- Python 编程经验
- 强大的 GPU（推荐 NVIDIA）
- 30+ GB 的可用磁盘空间

**说明：**
尝试在您自己的计算机上运行[此脚本](https://github.com/ifeimi/Whisper48/blob/main/WhisperX48_local.ipynb)。您需要先安装 PyTorch、WhisperX、FFmpeg 和其他依赖项。

⚠️ **注意：** 本地设置复杂，尚未充分测试。我们建议使用 Google Colab 代替。

---

## 📊 功能说明

### 什么使 Whisper48 与众不同？

**WhisperX 技术**：与标准 Whisper 不同，WhisperX 提供**字级时间戳**：
- 标准 Whisper："Hello world"（0:00-0:05）
- WhisperX："Hello"（0:00-0:02）"world"（0:02-0:05）

这种精确度可以实现更好的字幕同步和更专业的结果。

### 支持的语言
- 🇯🇵 日语（日本語）
- 🇨🇳 中文（中文）
- 🇬🇧 英语（English）
- 🇫🇷 法语（Français）
- 🇩🇪 德语（Deutsch）
- 🇪🇸 西班牙语（Español）
- 🇮🇹 意大利语（Italiano）
- 🇵🇹 葡萄牙语（Português）
- 🇷🇺 俄语（Русский）
- 以及更多...

### 支持的文件格式
- **音频**：MP3、WAV、M4A、AAC、FLAC
- **视频**：MP4、MKV、TS、FLV

---

## 📝 示例与样本输出

如需查看 WhisperX 与其他模型的比较，请查看此链接：[https://www.bilibili.com/video/BV1RFa5zhEeG/](https://www.bilibili.com/video/BV1RFa5zhEeG/)

---

## 🔧 工作原理（技术概述）

Whisper48 使用一个 3 步流程：

1. **语音识别**：OpenAI 的 Whisper 模型将音频转换为文本
2. **时间戳对齐**：WhisperX 使用 wav2vec2.0 将文本与精确的字级时间对齐
3. **字幕生成**：自动字幕格式化和下载

整个过程在 Google Colab 的免费 GPU 服务器上运行 - 您的计算机上无需安装任何东西！

---

## 🙋 支持与故障排查

### 获取帮助

- **网站**：详细指南和常见问题解答：[ifeimi.github.io/whisper48](https://ifeimi.github.io/whisper48/)
- **电子邮件**：联系开发者：yfwu0202 AT gmail DOT com
- **GitHub Issues**：在[项目的 issue 页面](https://github.com/ifeimi/Whisper48/issues)上报告 bug 或请求功能

---

## 📚 技术参考和致谢

### 基于以下项目：

本项目基于优秀的开源软件：

- **[WhisperX](https://github.com/m-bain/whisperX)**：改进了 OpenAI 的 Whisper，提供精确的字级时间戳
- **[OpenAI Whisper](https://github.com/openai/whisper)**：最先进的语音识别模型
- **[faster-whisper](https://github.com/guillaumekln/faster-whisper)**：优化的 Whisper 实现
- **[wav2vec2.0](https://huggingface.co/facebook/wav2vec2-large-960h-lv60-self)**：用于时间戳对齐的语音模型

### 项目起源

Whisper48 从 **N46Whisper** 项目分支而来，经过大幅修改以：
- 使用更准确的基于 Whisper 的模型（WhisperX）
- 改进日语支持
- 提供更好的时间戳精度
- 添加更多语言选项
- 简化用户界面

我们鼓励对本项目和上游项目的贡献！

---

## 📄 许可证和版权

本项目根据 **MIT 许可证** 发布。详见 [LICENSE.md](https://github.com/ifeimi/Whisper48/blob/main/LICENSE.md)。

### 署名

- 原始概念：[N46Whisper](https://github.com/Ayanaminn/N46Whisper) 作者 Ayanaminn
- 改进：WhisperX 集成和优化
- 代码改进：双语文档和界面增强

您可以自由地：
- ✅ 用于个人和商业项目
- ✅ 修改和重新分发
- ✅ 学习和研究代码

您必须：
- ✅ 包含许可证文本
- ✅ 注明原作者

---

## 📞 联系方式与支持

有问题或建议？请联系我们！

- **电子邮件**：ifeimi48 AT gmail DOT com
- **GitHub Issues**：[报告 bug 或请求功能](https://github.com/ifeimi/Whisper48/issues)
- **网站**：[ifeimi.github.io/whisper48](https://ifeimi.github.io/whisper48/)

我很乐意听取您的反馈并帮助解答任何问题！

---

**最后更新**：2026 年 1 月

![GitHub License](https://img.shields.io/github/license/ifeimi/Whisper48)
![GitHub Stars](https://img.shields.io/github/stars/ifeimi/Whisper48?style=social)

