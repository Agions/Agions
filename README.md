<!-- section:banner -->
<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/banner.svg" />
    <img src="assets/banner.svg" width="100%" alt="Agions — Full-Stack Developer & Video Tools Architect" />
  </picture>
</p>

<p align="center">
  <a href="https://github.com/Agions"><img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github" height="30" alt="GitHub"/></a>
  <a href="mailto:agions@qq.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" height="30" alt="Email"/></a>
</p>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=Agions&label=Profile%20Views&color=0A84FF&style=flat" alt="Profile Views" />
</p>
<!-- end:banner -->

---

<!-- section:about -->
## 👨‍💻 About Me

> **Full-Stack Developer**
>
> 聚焦跨平台桌面应用与视频处理工具链的开源开发。
> 技术栈以 **Rust**、**TypeScript**、**Python** 为核心，覆盖 Tauri 桌面端、AI 推理与全栈工程化。
> 作为 [Agions](https://github.com/Agions) GitHub 账号的维护者，致力于打造从视频采集、剪辑、字幕、解说到 AI 创作的全链路开源工具矩阵。

<p align="center">
  <img src="assets/profile-card.svg" width="300" alt="Profile Card" style="border-radius:16px;" />
</p>
<!-- end:about -->

---

<!-- section:ecosystem -->
## 🏗️ The Agions Stack

我的开源项目构成了一套完整的 **AI 视频处理生态**，各工具在不同环节协同工作：

```mermaid
flowchart LR
    subgraph Capture["📡 采集层"]
        SubLens["🔍 SubLens<br/>硬字幕提取"]
        A["🎙️ xfyun-sdk<br/>语音识别"]
        B["🔤 paddle-ocr.js<br/>OCR 引擎"]
    end

    subgraph Edit["✂️ 编辑层"]
        storyfab["✂️ story-fab<br/>AI 视频剪辑"]
        scenefab["🎙️ scene-fab<br/>AI 解说生成"]
        frameforge["🎬 frame-forge<br/>AI 视频创作"]
    end

    subgraph Infra["⚡ 基础设施层"]
        synerix["⚡ synerix<br/>AI 编程终端"]
        taskflow["🔧 taskflow-ai<br/>MCP 工作流引擎"]
        taroviz["📊 TaroViz<br/>多端图表"]
        orva["🎨 orva-ui<br/>跨平台 UI"]
    end

    Capture --> Edit
    Edit --> Infra
    
    style Capture fill:#0d1420,stroke:#0A84FF,color:#e6edf3
    style Edit fill:#0d1420,stroke:#30D158,color:#e6edf3
    style Infra fill:#0d1420,stroke:#BF5AF2,color:#e6edf3
```

<table>
  <tr>
    <th align="center" width="20%">Layer</th>
    <th align="center" width="40%">Projects</th>
    <th align="center" width="40%">Tech</th>
  </tr>
  <tr>
    <td align="center"><b>📡 Capture</b><br/><sub>内容采集</sub></td>
    <td>
      <a href="https://github.com/Agions/SubLens"><code>SubLens</code></a> ·
      <a href="https://github.com/Agions/xfyun-sdk"><code>xfyun-sdk</code></a> ·
      <a href="https://github.com/Agions/paddle-ocr.js"><code>paddle-ocr.js</code></a>
    </td>
    <td>
      <img src="https://img.shields.io/badge/Tauri-FFC131?logo=tauri&logoColor=black" height="20" alt="Tauri" />
      <img src="https://img.shields.io/badge/Rust-E8A838?logo=rust&logoColor=black" height="20" alt="Rust" />
      <img src="https://img.shields.io/badge/PaddleOCR-F05138?logo=paddlepaddle&logoColor=white" height="20" alt="PaddleOCR" />
    </td>
  </tr>
  <tr>
    <td align="center"><b>✂️ Edit</b><br/><sub>智能编辑</sub></td>
    <td>
      <a href="https://github.com/Agions/story-fab"><code>story-fab</code></a> ·
      <a href="https://github.com/Agions/scene-fab"><code>scene-fab</code></a> ·
      <a href="https://github.com/Agions/frame-forge"><code>frame-forge</code></a>
    </td>
    <td>
      <img src="https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white" height="20" alt="Python" />
      <img src="https://img.shields.io/badge/FFmpeg-00D4AA?logo=ffmpeg&logoColor=black" height="20" alt="FFmpeg" />
      <img src="https://img.shields.io/badge/PyTorch-EE4C2C?logo=pytorch&logoColor=white" height="20" alt="PyTorch" />
      <img src="https://img.shields.io/badge/Whisper-FF6F00?logo=openai&logoColor=white" height="20" alt="Whisper" />
    </td>
  </tr>
  <tr>
    <td align="center"><b>⚡ Infra</b><br/><sub>基础设施</sub></td>
    <td>
      <a href="https://github.com/Agions/synerix"><code>synerix</code></a> ·
      <a href="https://github.com/Agions/taskflow-ai"><code>taskflow-ai</code></a> ·
      <a href="https://github.com/Agions/TaroViz"><code>TaroViz</code></a> ·
      <a href="https://github.com/Agions/orva-ui"><code>orva-ui</code></a>
    </td>
    <td>
      <img src="https://img.shields.io/badge/Rust-E8A838?logo=rust&logoColor=black" height="20" alt="Rust" />
      <img src="https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white" height="20" alt="TypeScript" />
      <img src="https://img.shields.io/badge/Taro-5EBAFF?logo=taro&logoColor=white" height="20" alt="Taro" />
      <img src="https://img.shields.io/badge/NestJS-E0234E?logo=nestjs&logoColor=white" height="20" alt="NestJS" />
    </td>
  </tr>
</table>
<!-- end:ecosystem -->

---

<!-- section:projects -->
## 🚀 Featured Projects

<!-- scene-fab — flagship -->
<details open>
<summary><b>🎙️ scene-fab</b> — AI 影视解说创作工具 <sub><b>⭐ 295 · #1 by stars</b></sub></summary>
<br/>
<p align="left">
  <img src="https://img.shields.io/github/stars/Agions/scene-fab?style=flat&logo=github&label=Stars&color=30D158" alt="Stars"/>
  <img src="https://img.shields.io/github/forks/Agions/scene-fab?style=flat&logo=github&label=Forks&color=0A84FF" alt="Forks"/>
  <img src="https://img.shields.io/github/license/Agions/scene-fab?style=flat&label=License&color=BF5AF2" alt="License"/>
  <img src="https://img.shields.io/github/last-commit/Agions/scene-fab?style=flat&label=Updated&color=FFC107" alt="Last Commit"/>
  <br/>
  <b>Python · Whisper · PyTorch · FFmpeg · PyQt6 · TTS</b>
  <br/>
  🏆 <b>298 stars</b> · 🍴 <b>55 forks</b> · 端到端视频解说自动生成管线：语音识别 → AI 剧本生成 → 语音合成 → 视频渲染。
  支持第一人称叙事、多语言配音、一键发布。
  <br/>
  <a href="https://github.com/Agions/scene-fab"><code>📂 查看源码 →</code></a>
</p>
</details>

<!-- story-fab -->
<details open>
<summary><b>✂️ story-fab</b> — AI 视频剪辑工作站 <sub><b>⭐ 85</b></sub></summary>
<br/>
<p align="left">
  <img src="https://img.shields.io/github/stars/Agions/story-fab?style=flat&logo=github&label=Stars&color=30D158" alt="Stars"/>
  <img src="https://img.shields.io/github/forks/Agions/story-fab?style=flat&logo=github&label=Forks&color=0A84FF" alt="Forks"/>
  <img src="https://img.shields.io/github/license/Agions/story-fab?style=flat&label=License&color=BF5AF2" alt="License"/>
  <img src="https://img.shields.io/github/last-commit/Agions/story-fab?style=flat&label=Updated&color=FFC107" alt="Last Commit"/>
  <br/>
  <b>Tauri · React · TypeScript · Rust · FFmpeg · Whisper</b>
  <br/>
  🏆 <b>85 stars</b> · 🍴 <b>23 forks</b> · 长视频智能拆条为爆款短片段。9:16/1:1/16:9 多格式输出，
  本地 Whisper 字幕识别，Rust 高性能渲染管线，无需上传云端。
  <br/>
  <a href="https://github.com/Agions/story-fab"><code>📂 查看源码 →</code></a>
</p>
</details>

<!-- frame-forge -->
<details open>
<summary><b>🎬 frame-forge</b> — AI 视频创作工作室 <sub><b>⭐ 23</b></sub></summary>
<br/>
<p align="left">
  <img src="https://img.shields.io/github/stars/Agions/frame-forge?style=flat&logo=github&label=Stars&color=30D158" alt="Stars"/>
  <img src="https://img.shields.io/github/forks/Agions/frame-forge?style=flat&logo=github&label=Forks&color=0A84FF" alt="Forks"/>
  <img src="https://img.shields.io/github/license/Agions/frame-forge?style=flat&label=License&color=BF5AF2" alt="License"/>
  <img src="https://img.shields.io/github/last-commit/Agions/frame-forge?style=flat&label=Updated&color=FFC107" alt="Last Commit"/>
  <br/>
  <b>TypeScript · AI · LLM · Computer Vision · Text-to-Video</b>
  <br/>
  🏆 <b>23 stars</b> · 🍴 <b>10 forks</b> · AI-Driven Video Creation Studio.
  多模型协同生成视频内容，支持脚本生成、语音合成、自动渲染输出。
  <br/>
  <a href="https://github.com/Agions/frame-forge"><code>📂 查看源码 →</code></a>
</p>
</details>

<!-- SubLens -->
<details open>
<summary><b>🔍 SubLens</b> — 专业硬字幕提取工具 <sub><b>⭐ 15</b></sub></summary>
<br/>
<p align="left">
  <img src="https://img.shields.io/github/stars/Agions/SubLens?style=flat&logo=github&label=Stars&color=30D158" alt="Stars"/>
  <img src="https://img.shields.io/github/forks/Agions/SubLens?style=flat&logo=github&label=Forks&color=0A84FF" alt="Forks"/>
  <img src="https://img.shields.io/github/license/Agions/SubLens?style=flat&label=License&color=BF5AF2" alt="License"/>
  <img src="https://img.shields.io/github/last-commit/Agions/SubLens?style=flat&label=Updated&color=FFC107" alt="Last Commit"/>
  <br/>
  <b>Tauri · Rust · Vue 3 · TypeScript · PaddleOCR</b>
  <br/>
  🏆 <b>15 stars</b> · 🍴 <b>3 forks</b> · 高性能桌面端字幕提取引擎。
  支持批量处理、多语言识别（中/英/日/韩）、SRT/ASS/VTT 多格式导出。
  <br/>
  <a href="https://github.com/Agions/SubLens"><code>📂 查看源码 →</code></a>
</p>
</details>
<!-- end:projects -->

---

<!-- section:libraries -->
## 📦 Developer Libraries

<p align="center">
  <i>支撑上层应用的开源基础设施库</i>
</p>

<table>
  <tr>
    <th align="center" width="25%">Library</th>
    <th align="center" width="20%">Stars</th>
    <th align="center" width="30%">Description</th>
    <th align="center" width="25%">Tech Stack</th>
  </tr>
  <tr>
    <td><b>⚡ synerix</b></td>
    <td><img src="https://img.shields.io/github/stars/Agions/synerix?style=flat&label=&color=FFC107" alt="stars"/></td>
    <td>高性能 AI 编程终端 · 多智能体协作 + TUI + 沙箱</td>
    <td><code>Rust</code> <code>Ratatui</code> <code>MCP</code></td>
  </tr>
  <tr>
    <td><b>🔧 taskflow-ai</b></td>
    <td><img src="https://img.shields.io/github/stars/Agions/taskflow-ai?style=flat&label=&color=FFC107" alt="stars"/></td>
    <td>Pure MCP Server for Claude Desktop, Cursor & Windsurf</td>
    <td><code>TypeScript</code> <code>MCP</code></td>
  </tr>
  <tr>
    <td><b>📊 TaroViz</b></td>
    <td><img src="https://img.shields.io/github/stars/Agions/TaroViz?style=flat&label=&color=FFC107" alt="stars"/></td>
    <td>多端图表组件库，Taro + ECharts，支持小程序和 H5</td>
    <td><code>TypeScript</code> <code>Taro</code> <code>ECharts</code></td>
  </tr>
  <tr>
    <td><b>🎨 orva-ui</b></td>
    <td><img src="https://img.shields.io/github/stars/Agions/orva-ui?style=flat&label=&color=FFC107" alt="stars"/></td>
    <td>React/Taro 跨平台 UI 组件库，90+ 组件</td>
    <td><code>TypeScript</code> <code>React</code> <code>Taro</code></td>
  </tr>
  <tr>
    <td><b>🖨️ taro-bluetooth-print</b></td>
    <td><img src="https://img.shields.io/github/stars/Agions/taro-bluetooth-print?style=flat&label=&color=FFC107" alt="stars"/></td>
    <td>Taro 蓝牙打印库，支持 ESC/POS、TSPL、ZPL、CPCL</td>
    <td><code>TypeScript</code> <code>Taro</code></td>
  </tr>
  <tr>
    <td><b>🎙️ xfyun-sdk</b></td>
    <td><img src="https://img.shields.io/github/stars/Agions/xfyun-sdk?style=flat&label=&color=FFC107" alt="stars"/></td>
    <td>科大讯飞语音识别 WebAPI 的 JS/TS SDK</td>
    <td><code>TypeScript</code></td>
  </tr>
  <tr>
    <td><b>🔤 paddle-ocr.js</b></td>
    <td><img src="https://img.shields.io/github/stars/Agions/paddle-ocr.js?style=flat&label=&color=FFC107" alt="stars"/></td>
    <td>飞桨 PaddleOCR 的 JS 封装，浏览器和 Node.js</td>
    <td><code>TypeScript</code></td>
  </tr>
</table>
<!-- end:libraries -->

---

<!-- section:tech-stack -->
## 🛠️ Tech Radar

<p align="center">
  <sub>点击 badge 导航到相关项目</sub>
</p>

<p align="center">
  <a href="https://github.com/Agions?tab=repositories&q=&type=&language=rust"><img src="https://img.shields.io/badge/Rust-E8A838?style=for-the-badge&logo=rust&logoColor=black" alt="Rust"/></a>
  <a href="https://github.com/Agions?tab=repositories&q=&type=&language=typescript"><img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript"/></a>
  <a href="https://github.com/Agions?tab=repositories&q=&type=&language=python"><img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/></a>
  <a href="https://github.com/Agions?tab=repositories&q=&type=&language=html"><img src="https://img.shields.io/badge/HTML-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML"/></a>
</p>

| Category | Technologies | Powered Projects |
|----------|-------------|-----------------|
| 🖥️ **Desktop** | Tauri · Rust · Vue 3 · React · PyQt6 | SubLens · story-fab · scene-fab |
| 🌐 **Web / Mini-App** | TypeScript · React · Taro · NestJS · MongoDB | TaroViz · orva-ui · taro-bluetooth-print |
| 🧠 **AI / ML** | Python · PyTorch · Whisper · TTS · PaddleOCR | scene-fab · SubLens · paddle-ocr.js |
| 🔧 **Dev Tools** | Rust · Ratatui · MCP · Node.js · FFmpeg · Docker | synerix · taskflow-ai · xfyun-sdk |
| 🚀 **CI / DX** | GitHub Actions · Prettier · ESLint · Stylelint | All Projects |
<!-- end:tech-stack -->

---

<!-- section:analytics -->
## 📈 GitHub Analytics

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api?username=Agions&show_icons=true&count_private=true&hide_border=true&bg_color=0d1117&title_color=0A84FF&icon_color=30D158&text_color=e6edf3&ring_color=0A84FF&include_all_commits=true&custom_title=Agions·GitHub+Stats" />
    <img src="https://github-readme-stats.vercel.app/api?username=Agions&show_icons=true&count_private=true&hide_border=true&bg_color=ffffff&title_color=0A84FF&icon_color=30D158&text_color=333333&ring_color=0A84FF&include_all_commits=true&custom_title=Agions·GitHub+Stats" height="180" alt="GitHub Stats" />
  </picture>
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api/top-langs/?username=Agions&layout=compact&hide_border=true&bg_color=0d1117&title_color=0A84FF&text_color=e6edf3&langs_count=6" />
    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Agions&layout=compact&hide_border=true&bg_color=ffffff&title_color=0A84FF&text_color=333333&langs_count=6" height="180" alt="Top Languages" />
  </picture>
</p>

<p align="center">
  <img src="https://github-profile-trophy.vercel.app/?username=Agions&theme=onedark&no-frame=true&no-bg=true&row=1&column=7" width="100%" alt="GitHub Trophies" />
</p>
<!-- end:analytics -->

---

<!-- section:activity -->
## 🌊 Contribution Activity

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-activity-graph.vercel.app/graph?username=Agions&theme=react-dark&hide_border=true&bg_color=0d1117&color=0A84FF&line=30D158&point=BF5AF2&custom_title=Agions·Contribution+Graph" />
    <img src="https://github-readme-activity-graph.vercel.app/graph?username=Agions&theme=default&hide_border=true&bg_color=ffffff&color=0A84FF&line=30D158&point=BF5AF2&custom_title=Agions·Contribution+Graph" width="100%" alt="Contribution Graph" />
  </picture>
</p>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Agions/Agions/main/output/snake.svg" />
    <img src="https://raw.githubusercontent.com/Agions/Agions/main/output/snake.svg" alt="Contribution Snake Animation" />
  </picture>
</p>

<p align="center">
  <a href="https://github.com/Agions"><img src="https://img.shields.io/github/contributors/Agions/Agions?style=flat&logo=github&label=Contributors&color=0A84FF" alt="Contributors"/></a>
  <a href="https://github.com/Agions/Agions"><img src="https://img.shields.io/github/last-commit/Agions/Agions?style=flat&logo=github&label=Last%20Updated&color=30D158" alt="Last Updated"/></a>
  <a href="https://github.com/Agions/Agions"><img src="https://img.shields.io/github/repo-size/Agions/Agions?style=flat&logo=github&label=Repo%20Size&color=FFC107" alt="Repo Size"/></a>
  <a href="https://github.com/Agions/Agions/commits/main"><img src="https://img.shields.io/github/commit-activity/t/Agions/Agions?style=flat&logo=github&label=Commits&color=BF5AF2" alt="Commit Activity"/></a>
</p>
<!-- end:activity -->

---

<!-- section:contact -->
## 📬 Let's Connect

<p align="center">
  <img src="assets/wechat-qrcode.png" width="120" alt="WeChat QR Code" style="border-radius:10px;"/>
  <br/>
  <sub>📱 WeChat 公众号</sub>
</p>

<p align="center">
  <sub>💬 反馈与建议 · 开源合作 · 项目交流</sub>
</p>
<!-- end:contact -->

---

<!-- section:footer -->
<p align="center">
  <img src="https://img.shields.io/badge/Made%20with-%E2%9D%A4%EF%B8%8F%20and%20%E2%98%95-E8A838?style=flat" alt="Made with ❤️ and ☕"/>
</p>

<p align="center">
  <sub>⚡ Agions · Building the next generation of video tools · Since 2017</sub>
</p>
<!-- end:footer -->