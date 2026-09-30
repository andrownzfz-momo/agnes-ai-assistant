# Agnes AI 助手 - Vercel 部署版

仿照 https://vp5f1qceb.666freevps.cn/?i/2 项目，纯前端单文件 AI 助手应用。

## 功能

- **对话** - 与 AI 模型多轮对话
- **文生图** - 文本生成图片（多种风格/尺寸/画质）
- **图生图** - 图片编辑/多参考图合成
- **文生视频** - 文本生成视频
- **单图生视频** - 图片生成视频
- **多图生视频** - 多图参考生成视频
- **首尾帧生视频** - 首尾帧插值生成视频
- **生成短剧** - 多步骤短剧生成工作流
- **画布** - 节点式工作流编辑器
- **API Key 池** - 多 Key 轮询、自动冷却、并发控制

## 技术栈

- 纯 HTML/CSS/JavaScript（无框架依赖）
- 单文件应用（所有代码内联）
- localStorage 持久化配置
- 调用 Agnes AI API

## 部署到 Vercel

### 方法一：Vercel CLI

```bash
npm i -g vercel
vercel
```

### 方法二：Git 集成

1. 将代码推送到 GitHub/GitLab 仓库
2. 在 Vercel 控制台导入项目
3. 框架选择 "Other"，直接部署

### 方法三：直接部署

```bash
vercel --prod
```

## 配置

1. 部署后访问网站
2. 点击右上角 **设置**
3. 输入 Agnes AI API Key（支持多个，每行一个）
4. 设置 Base URL（默认 `https://api.agnes-ai.cn/v1`）
5. 点击 **保存并连接**

## 文件结构

```
.
├── index.html      # 主应用文件（包含所有 HTML/CSS/JS）
├── vercel.json     # Vercel 部署配置
└── README.md       # 说明文档
```

## 注意事项

- API Key 存储在浏览器 localStorage 中，不会上传到服务器
- 所有 API 请求直接从浏览器发起（需确保 API 支持 CORS）
- 视频生成采用异步轮询机制，生成时间较长
- 建议配置多个 API Key 以提高并发能力和稳定性
