# Mobile Next - MCP server 移动开发与自动化 MCP 服务端 | iOS, Android, Simulator, Emulator, and Real Devices

这是一个**模型上下文协议（MCP）服务端**，它通过平台无关的接口实现了可扩展的移动自动化与开发，无需开发者具备 iOS 或 Android 的专门知识。该服务端可在模拟器、仿真器及真实设备（iOS 和 Android）上运行。

它允许智能体客户端与大语言模型通过结构化的无障碍界面快照或基于屏幕截图的坐标点击，与原生 iOS/Android 应用及设备进行交互。

<h4 align="center">
  <a href="https://github.com/mobile-next/mobile-mcp">
    <img src="https://img.shields.io/github/stars/mobile-next/mobile-mcp" alt="Mobile Next Stars" />
  </a>
  <a href="https://github.com/mobile-next/mobile-mcp">
    <img src="https://img.shields.io/github/contributors/mobile-next/mobile-mcp?color=green" alt="Mobile Next Downloads" />
  </a>
  <a href="https://www.npmjs.com/package/@mobilenext/mobile-mcp">
    <img src="https://img.shields.io/npm/dm/@mobilenext/mobile-mcp?logo=npm&style=flat&color=red" alt="npm" />
  </a>
  <a href="https://github.com/mobile-next/mobile-mcp/releases">
    <img src="https://img.shields.io/github/release/mobile-next/mobile-mcp" />
  </a>
  <a href="https://github.com/mobile-next/mobile-mcp/blob/main/LICENSE">
    <img src="https://img.shields.io/badge/license-Apache 2.0-blue.svg" alt="Mobile MCP is released under the Apache-2.0 License" />
  </a>
  <a href="https://insiders.vscode.dev/redirect?url=vscode%3Amcp%2Finstall%3F%7B%22name%22%3A%22mobile-mcp%22%2C%22command%22%3A%22npx%22%2C%22args%22%3A%5B%22-y%22%2C%22%40mobilenext%2Fmobile-mcp%40latest%22%5D%7D">
    <img src="https://img.shields.io/badge/VS_Code-VS_Code?style=flat-square&label=Install%20Server&color=0098FF" alt="Install in VS Code" />
  </a>
</h4>


<h4 align="center">
  <a href="https://github.com/mobile-next/mobile-mcp/wiki">
    <img src="https://img.shields.io/badge/documentation-wiki-blue" alt="wiki" />
  </a>
  <a href="http://mobilenexthq.com/join-slack">
    <img src="https://img.shields.io/badge/join-Slack-blueviolet?logo=slack&style=flat" alt="join on Slack" />
  </a>
</h4>


https://github.com/user-attachments/assets/c4e89c4f-cc71-4424-8184-bdbc8c638fa1

<p align="center">
    <a href="https://github.com/mobile-next/">
        <img alt="mobile-mcp" src="https://raw.githubusercontent.com/mobile-next/mobile-next-assets/refs/heads/main/mobile-mcp-banner.png" width="600" />
    </a>
</p>

### 🚀 移动MCP发展规划：构建移动智能交互的未来

**加入我们，共同见证 Mobile MCP 的持续进化！**

欢迎查阅我们的详细规划，了解即将推出的功能特性、优化计划与发展里程碑。您的反馈将为移动自动化的未来勾勒方向，每一份建议都不可或缺。

👉 [Explore the Roadmap](https://github.com/orgs/mobile-next/projects/3)

### 核心应用场景

我们如何助力移动自动化规模化：

- 📲 **原生APP自动化**（iOS 与 Android），适用于测试或数据录入场景
- 📝 **脚本化流程与表单交互**，无需手动操控模拟器/仿真器或真实设备（iPhone、三星、Google Pixel 等）
- 🧭 **多步骤用户流程自动化**，由大语言模型（LLM）驱动执行
- 👆 **通用移动应用交互**，为基于智能体的框架提供支持
- 🤖 **实现智能体间通信**，服务于移动自动化用例与数据提取任务

## 主要特性

- 🚀 **快速轻量**：多数交互基于原生无障碍树实现，当无障碍标签不可用时，支持基于截图坐标的替代方案。
- 🤖 **大语言模型友好**：在无障碍（快照）模式下，无需计算机视觉模型辅助。
- 🧿 **视觉感知**：通过评估与分析屏幕实际渲染内容，智能决策下一步操作。若无障碍数据或视图层级坐标不可用，将自动回退至基于截图的视觉分析。
- 📊 **确定性工具应用**：尽可能依赖结构化数据，减少纯截图方案中常见的模糊性与不确定性。
- 📺 **结构化数据提取**：支持从屏幕可见内容中提取结构化数据。

## 🔧 可用的 MCP 工具

<details>
<summary>📱 <strong>点击展开工具列表</strong> - 用于自动化与开发的移动 MCP 工具列表</summary>


> 关于具体实现与参数说明，请参阅 [`src/server.ts`](src/server.ts)

### Device Management

- **`mobile_list_available_devices`** - List all available devices (simulators, emulators, and real devices)
- **`mobile_get_screen_size`** - Get the screen size of the mobile device in pixels
- **`mobile_get_orientation`** - Get the current screen orientation of the device
- **`mobile_set_orientation`** - Change the screen orientation (portrait/landscape)

### App Management

- **`mobile_list_apps`** - List all installed apps on the device
- **`mobile_launch_app`** - Launch an app using its package name
- **`mobile_terminate_app`** - Stop and terminate a running app
- **`mobile_install_app`** - Install an app from file (.apk, .ipa, .app, .zip)
- **`mobile_uninstall_app`** - Uninstall an app using bundle ID or package name

### Screen Interaction

- **`mobile_take_screenshot`** - Take a screenshot to understand what's on screen
- **`mobile_save_screenshot`** - Save a screenshot to a file
- **`mobile_list_elements_on_screen`** - List UI elements with their coordinates and properties
- **`mobile_click_on_screen_at_coordinates`** - Click at specific x,y coordinates
- **`mobile_double_tap_on_screen`** - Double-tap at specific coordinates
- **`mobile_long_press_on_screen_at_coordinates`** - Long press at specific coordinates
- **`mobile_swipe_on_screen`** - Swipe in any direction (up, down, left, right)

### Input & Navigation

- **`mobile_type_keys`** - Type text into focused elements with optional submit
- **`mobile_press_button`** - Press device buttons (HOME, BACK, VOLUME_UP/DOWN, ENTER, etc.)
- **`mobile_open_url`** - Open URLs in the device browser

### Platform Support

- **iOS**: Simulators and real devices via native accessibility and WebDriverAgent
- **Android**: Emulators and real devices via ADB and UI Automator
- **Cross-platform**: Unified API works across both iOS and Android

</details>

## 🏗️ Mobile MCP 架构

<p align="center">
    <a href="https://raw.githubusercontent.com/mobile-next/mobile-next-assets/refs/heads/main/mobile-mcp-arch-1.png">
        <img alt="mobile-mcp" src="https://raw.githubusercontent.com/mobile-next/mobile-next-assets/refs/heads/main/mobile-mcp-arch-1.png" width="600">
    </a>
</p>



## 📚 Wiki 页面

更详细的设置、配置和调试相关问题，请参阅我们的 Wiki 页面 [wiki page](https://github.com/mobile-next/mobile-mcp/wiki) 。


## 安装和配置

在大多数工具/平台中的**标准配置**:

```json
{
  "mcpServers": {
    "mobile-mcp": {
      "command": "npx",
      "args": ["-y", "@mobilenext/mobile-mcp@latest"]
    }
  }
}
```

<details>
<summary>Amp</summary>

通过 Amp VS Code 扩展的设置界面，或直接更新 `settings.json`配置文件：

```json
"amp.mcpServers": {
  "mobile-mcp": {
    "command": "npx",
    "args": [
      "@mobilenext/mobile-mcp@latest"
    ]
  }
}
```

**Amp CLI:**

在终端中执行以下命令

```bash
amp mcp add mobile-mcp -- npx @mobilenext/mobile-mcp@latest
```

</details>

<details>
<summary>Cline</summary>

**Cline 配置方法**：将上述 JSON 配置添加到您的 MCP 设置文件中即可完成设置。

[More in our wiki](https://github.com/mobile-next/mobile-mcp/wiki/Cline)

</details>

<details>
<summary>Claude Code</summary>

**Claude Code CLI 配置 Mobile MCP server方法：**

```bash
claude mcp add mobile-mcp -- npx -y @mobilenext/mobile-mcp@latest
```

</details>

<details>
<summary>Claude Desktop</summary>


请参考 [MCP install guide](https://modelcontextprotocol.io/quickstart/user), 并使用上面的json配置.

</details>

<details>
<summary>Codex</summary>

在Codex CLI中添加Mobile MCP server:

```bash
codex mcp add mobile-mcp npx "@mobilenext/mobile-mcp@latest"
```

或者，创建或编辑配置文件 `~/.codex/config.toml`并添加以下内容：

```toml
[mcp_servers.mobile-mcp]
command = "npx"
args = ["@mobilenext/mobile-mcp@latest"]
```

更多信息，请查看Codex MCP documentation.

</details>

<details>
<summary>Copilot</summary>


使用 Copilot CLI 以交互方式添加 Mobile MCP 服务器：

```text
/mcp add
```

您可以编辑配置文件 `~/.copilot/mcp-config.json` 并添加以下内容：

```json
{
  "mcpServers": {
    "mobile-mcp": {
      "type": "local",
      "command": "npx",
      "tools": [
        "*"
      ],
      "args": [
        "@mobilenext/mobile-mcp@latest"
      ]
    }
  }
}
```

更多信息请查看 Copilot CLI 文档.

</details>

<details>
<summary>Cursor</summary>


#### 点击下面的按钮安装:

[<img src="https://cursor.com/deeplink/mcp-install-dark.svg" alt="Install in Cursor">](https://cursor.com/en/install-mcp?name=Mobile%20MCP&config=eyJjb21tYW5kIjoibnB4IiwiYXJncyI6WyIteSIsIkBtb2JpbGVuZXh0L21vYmlsZS1tY3BAbGF0ZXN0Il19)

#### 或手动安装:

请按以下步骤在 Cursor 中添加 Mobile MCP 服务器：

- 打开 `Cursor Settings` -> `MCP` -> `Add new MCP Server`. 
- 名称：可自定义（例如 "mobile-mcp"）
- **命令类型**：选择 "command"
- 填入 `npx -y @mobilenext/mobile-mcp@latest`。
- （可选）如需验证配置或添加命令行参数，可点击 **编辑** 进行高级设置。

</details>

<details>
<summary>Gemini CLI</summary>


使用 Gemini CLI 添加 Mobile MCP 服务器：

```bash
gemini mcp add mobile-mcp npx -y @mobilenext/mobile-mcp@latest
```

</details>

<details>
<summary>Goose</summary>


#### 点击下面的按钮安装:

[![Install in Goose](https://block.github.io/goose/img/extension-install-dark.svg)](https://block.github.io/goose/extension?cmd=npx&arg=-y&arg=%40mobilenext%2Fmobile-mcp%40latest&id=mobile-mcp&name=Mobile%20MCP&description=Mobile%20automation%20and%20development%20for%20iOS%2C%20Android%2C%20simulators%2C%20emulators%2C%20and%20real%20devices)

#### 或手动安装:

Go to `Advanced settings` -> `Extensions` -> `Add custom extension`. Name to your liking, use type `STDIO`, and set the `command` to `npx -y @mobilenext/mobile-mcp@latest`. Click "Add Extension".

请按以下步骤添加自定义扩展：

- 进入 `Advanced settings` -> `Extensions` -> `Add custom extension`。
- **名称**：可自定义（如 "mobile-mcp"）。
- **类型**：选择 `STDIO`（标准输入/输出）。
- **命令**：设置为 `npx -y @mobilenext/mobile-mcp@latest`。
- 点击 **"添加扩展"** 完成配置。

</details>

<details>
<summary>Kiro</summary>


请遵循 MCP 服务器的 官方文档进行配置。例如，在 `.kiro/settings/mcp.json`文件中添加如下配置：

```json
{
  "mcpServers": {
    "mobile-mcp": {
      "command": "npx",
      "args": [
        "@mobilenext/mobile-mcp@latest"
      ]
    }
  }
}
```

</details>

<details>
<summary>opencode</summary>


请遵循 MCP 服务器的 官方文档进行配置。例如，在 `~/.config/opencode/opencode.json`文件中添加如下配置：

```json
{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
    "mobile-mcp": {
      "type": "local",
      "command": [
        "npx",
        "@mobilenext/mobile-mcp@latest"
      ],
      "enabled": true
    }
  }
}
```

</details>

<details>
<summary>Qodo Gen</summary>


Open [Qodo Gen](https://docs.qodo.ai/qodo-documentation/qodo-gen) chat panel in VSCode or IntelliJ → Connect more tools → + Add new MCP → Paste the standard config above.

Click <code>Save</code>.

在 VSCode 或 IntelliJ 中打开 [Qodo Gen](https://docs.qodo.ai/qodo-documentation/qodo-gen) 聊天面板 → Connect more tools → + Add new MCP → 粘贴上方的标准配置.

点击保存.

</details>


<details>
<summary>Windsurf</summary>

打开 Windsurf 设置，导航至 MCP 服务器选项，使用 `command`类型添加新服务器，配置如下：

- **打开设置**：启动 Windsurf IDE 并进入设置界面

- **定位菜单**：在侧边栏或设置面板中找到 "MCP servers" 选项

- **添加服务器**：点击添加按钮，选择 `command`作为服务器类型

- **输入命令**：在命令字段中填入 

```bash
npx @mobilenext/mobile-mcp@latest
```

或者，如上文所示，在您配置文件的 `mcpServers`节点下添加标准配置。

</details>


[Read more in our wiki](https://github.com/mobile-next/mobile-mcp/wiki)! 🚀

### 🛠️ 使用指南 📝

将 MCP 服务器添加到您的 IDE/客户端后，即可指示 AI 助手调用可用工具。

例如，在 Cursor 的智能体模式下，您可以使用以下提示词快速验证、测试并迭代 UI 交互，读取屏幕信息，完成复杂工作流程：

**核心原则**：描述清晰，直击要点。

### ✨ 提示词示例

#### 工作流程

您可以在单条提示词中指定详细的工作流程，验证业务逻辑，设置自动化任务。发挥空间很大：

**搜索视频、发表评论、点赞并分享。**

```
查找名为 "Beginner Recipe for Tonkotsu Ramen" 的视频（作者：Way of Ramen），点击点赞，点赞后在评论区留言 "这看起来太美味了，下周五就尝试制作"，并将该视频分享给 WhatsApp 联系人列表中的第一位好友。
```

**下载一款有效的计步应用，完成注册，设置运动计划，并给予该应用五星好评。**

```
查找并下载一款免费、评分超过 1k 星的 "Pomodoro" 应用。启动应用，使用我的邮箱完成注册，注册后找到如何启动番茄钟计时器。当计时器启动后，返回应用商店，给该应用五星好评，并留言说明其实用性。
```

**在 Substack 中搜索文章，阅读内容，高亮标记，发表评论并保存文章。**

```
打开 Substack 网站，搜索"Latest trends in AI automation 2025"，打开第一篇文章，高亮标出标题为"Emerging AI trends"的章节，将文章保存至稍后阅读列表，并随机选取一段内容发表摘要评论。
```

**预订一节健身课程，并设置计时器。**

```
打开 ClassPass 应用，搜索明天上午 2 英里内的瑜伽课程，预订评分最高的 7 点课程，确认预约，并在手机中为预约时段设置计时器。
```

**查找本地活动，并创建日历事项。**

```
打开 Eventbrite，搜索本周末在德克萨斯州奥斯汀市举行的 AI 初创公司见面会活动，选择最受欢迎的一个，完成注册并点击"参加"，同时设置日历事项作为提醒。
```

**查看天气预报，并发送 WhatsApp/Telegram/Slack 消息。**

```
打开天气应用，查看柏林明天的天气预报，并通过 WhatsApp/Telegram/Slack 将天气摘要发送给联系人 "Lauren Trown"，并点赞对方的回复。
```

**在 Zoom 中预约会议，并通过邮件发送邀请。**

```
打开 Zoom 应用，为明天上午 10 点创建一个标题为"AI Hackathon"、时长 1 小时的会议，复制会议邀请链接，并通过 Gmail 将其发送给联系人 "team@example.com"。
```

[More prompt examples can be found here.](https://github.com/mobile-next/mobile-mcp/wiki/Prompt-Example-repo-list)

## 前置要求

- 连接 MCP 到您的智能体与移动设备所需条件：
  - **Xcode 命令行工具**（macOS）
  - **Android 平台工具**（ADB）
  - **Node.jsv22+** 运行环境
  - 支持 **MCP 协议** 的基础模型或智能体，例如：[Claude MCP](https://modelcontextprotocol.io/quickstart/server), [OpenAI Agent SDK](https://openai.github.io/openai-agents-python/mcp/), [Copilot Studio](https://www.microsoft.com/en-us/microsoft-copilot/blog/copilot-studio/introducing-model-context-protocol-mcp-in-copilot-studio-simplified-integration-with-ai-apps-and-agents/)

### 模拟器、仿真器与真实设备

Mobile MCP 启动后，可连接至：

- **iOS 仿真器**（macOS/Linux）
- **Android 模拟器**（Linux/Windows/macOS）
- **iOS 或 Android 真实设备**（需安装对应平台工具与驱动）

在运行 Mobile Next MCP 前，请确保已正确安装并配置移动平台 SDK（Xcode、Android SDK）

### 在模拟器/仿真器上以"无头"模式运行

当您的机器未连接真实设备时，可在后台运行模拟器/仿真器并使用 Mobile MCP。

**Android 示例**：

1. 启动模拟器（通过 avdmanager / emulator 命令）
2. 使用相应参数运行 Mobile MCP

**iOS 示例**（需先运行 Xcode 仿真器）：

- 查看可用仿真器：`xcrun simctl list`
- 启动特定设备：`xcrun simctl boot "iPhone 16"`

# 感谢所有贡献者 ❤️

### 我们衷心感谢每一位帮助改进此项目的伙伴。

  <a href = "https://github.com/mobile-next/mobile-mcp/graphs/contributors">
   <img src = "https://contrib.rocks/image?repo=mobile-next/mobile-mcp"/>
 </a>
