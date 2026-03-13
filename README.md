# 微信聊天记录识别工具

一个基于 AI 的微信聊天记录截图识别工具，支持自动识别聊天内容并导出为文本或 Word 文档。
目前还在处理上传GitHub的代码安全问题，但已经部署到railway上


## 功能特性

- 📸 **截图上传** - 支持上传微信聊天截图，自动检测长截图并分片处理
- 🤖 **AI 识别** - 支持多种 AI 服务商（OpenAI、Claude、通义千问、智谱AI）
- 🆓 **免费模型** - 提供免费的 GLM-4.6V 模型，每日 10 次使用额度
- 📝 **结果导出** - 支持导出为 TXT 或 DOCX 格式
- 🔐 **安全加密** - API 密钥加密存储，JWT 认证
- 🌐 **全栈部署** - 支持一键部署到 Railway

## 技术栈

### 前端
- React 18 + TypeScript
- Ant Design 5
- Zustand (状态管理)
- Vite (构建工具)

### 后端
- Node.js + Express + TypeScript
- SQLite (sql.js)
- JWT 认证
- AES-256 加密

### AI 服务
- OpenAI GPT-4o
- Anthropic Claude 3
- 阿里通义千问
- 智谱 GLM-4.6V

## 快速开始

### 本地开发

```bash
# 克隆仓库
git clone https://github.com/Xyihang/WECHAT.git
cd WECHAT

# 安装依赖
npm install

# 配置环境变量
cp backend/.env.example backend/.env
# 编辑 backend/.env 设置必要的环境变量

# 启动开发服务器
npm run dev
```

访问 http://localhost:3000 使用应用。

### 环境变量

| 变量名 | 说明 | 是否必须 |
|--------|------|----------|
| `JWT_SECRET` | JWT 签名密钥 | **是** |
| `ENCRYPTION_KEY` | API 密钥加密密钥 | **是** |
| `DEVELOPER_GLM_KEY` | 免费模型 API 密钥 | **是** |

生成密钥：
```bash
openssl rand -base64 32
```


## 项目结构

```
WECHAT/
├── frontend/                # 前端代码
│   ├── src/
│   │   ├── components/      # 组件
│   │   ├── pages/           # 页面
│   │   ├── services/        # API 服务
│   │   └── stores/          # 状态管理
│   └── package.json
├── backend/                 # 后端代码
│   ├── src/
│   │   ├── routes/          # 路由
│   │   ├── services/        # 业务逻辑
│   │   ├── middleware/      # 中间件
│   │   └── utils/           # 工具函数
│   └── package.json
├── Dockerfile               # Docker 构建文件
├── railway.json             # Railway 配置
└── package.json             # 根目录脚本
```

## 使用说明

### 1. 注册/登录
首次使用需要注册账号，管理员可以通过管理后台管理用户。

### 2. 配置 API 密钥（可选）
- 进入设置页面
- 选择 AI 服务商
- 输入 API 密钥
- 保存配置

### 3. 上传截图
- 支持拖拽或点击上传
- 自动检测长截图并分片
- 支持批量上传

### 4. 开始识别
- 选择 AI 服务商
- 可自定义提示词
- 点击开始识别

### 5. 导出结果
- 复制到剪贴板
- 导出为 TXT 文件
- 导出为 Word 文档

## 安全特性

- ✅ JWT Token 认证
- ✅ API 密钥 AES-256 加密存储
- ✅ 密码 bcrypt 哈希
- ✅ CORS 跨域保护
- ✅ 速率限制
- ✅ Helmet 安全头
- ✅ 文件上传验证

## 免费模型说明

本项目提供免费的 GLM-4.6V 模型供用户体验：
- 每日 10 次使用额度
- 并发限制 10 人
- 高峰期可能需要等待
- 不支持自定义提示词

## 常见问题

### Q: 免费模型无法使用？
A: 检查是否已登录，每日额度是否用完。

### Q: 识别结果不准确？
A: 尝试使用自定义提示词，或切换到其他 AI 服务商。

### Q: 如何获取 API 密钥？
A: 
- OpenAI: https://platform.openai.com/api-keys
- Claude: https://console.anthropic.com/
- 通义千问: https://dashscope.console.aliyun.com/
- 智谱AI: https://open.bigmodel.cn/

## 许可证

MIT License

## 贡献

欢迎提交 Issue 和 Pull Request！

## 联系方式

- GitHub: https://github.com/Xyihang/WECHAT
