# Taro 跨端脚手架 Prompt 完整文档 v1

## 使用说明

下面有两个代码块：
1. **第一个代码块**：介绍文章（可以发布到博客/社区）
2. **第二个代码块**：AI Prompt 提示词（复制后发给 Claude/GPT-4 等 AI）

用户可以直接复制对应代码块中的内容使用。

---

## 📄 文档一：介绍文章

```markdown
# AI 时代，小白也能 10 分钟搭建全栈项目｜Taro 跨端脚手架 Prompt 分享

> 📢 **AI 提示词，让零基础小白也能生成专业级的 Taro + Node.js 全栈项目，让你成为全栈工程师的路上踏出第一步。**

---

## 🎯 这篇文章写给谁？

也许你是：
- 👔 想做副业的上班族，有想法但不会写代码
- 🚀 想验证 MVP 的创业者，不想花钱请外包
- 🎓 想学全栈的学生，不知道从哪开始
- 🔄 想从其他行业转行的朋友，觉得编程门槛太高

**我相信在 AI 时代，技术不应该成为实现想法的门槛。**

这份提示词就是为了帮助你——只要你有想法，AI + 这份提示词，就能帮你迈出全栈开发的第一步。

---

### 💡 我的初衷

我不是科班出身的程序员，但我相信在 AI 时代，**技术不应该成为实现想法的门槛**。

很多人有好的产品想法，却因为不会全栈开发而放弃。我希望这份提示词能成为一座桥梁，让更多人迈出第一步。

### 我的背景

日常用 Vue 开发，一码多端选择的 uni-app。

最近想尝试 **React + Taro** 技术栈。但从 Vue 切到 React，配置、写法都不一样。

于是尝试用 AI 来帮我生成项目脚手架，效果出乎意料！


### 🙋 邀请你一起完善

这份提示词不是终点，而是一个起点。它还有很多可以改进的地方：

- 🗄️ 支持更多数据库（MySQL、MongoDB）
- 📱 支持更多小程序平台（支付宝、抖音、快手）
- 🧩 增加更多业务模块模板（支付、文件上传、消息推送）
- 🎨 优化 UI 组件和样式
- ...

**欢迎你参与贡献：**

| 你的情况 | 欢迎你 |
|----------|--------|
| 试用后发现了 Bug | 提 Issue 反馈 |
| 有更好的配置方案 | 提 PR 改进 |
| 想增加新功能模块 | Fork 后扩展，欢迎分享 |
| 成功上线了产品 | **在评论区分享你的故事！** |

**让我们一起，用 AI 降低技术门槛，让更多人能把想法变成现实。**

---

## 🛠️ 小白必看：电脑环境准备

在开始之前，请确保你的电脑安装了以下工具：

### 1. Node.js（必装）
- **作用**：运行 JavaScript/TypeScript 代码
- **版本要求**：18.0 或更高
- **下载地址**：https://nodejs.org/
- **验证安装**：打开终端输入 `node -v`，显示版本号即成功

### 2. pnpm（必装）
- **作用**：包管理工具，比 npm 更快更省空间
- **安装命令**：
  > ⚠️ **Windows 用户注意**：请右键「以管理员身份运行」命令提示符或 PowerShell，否则可能安装失败！
  ```bash
  npm install -g pnpm
  ```
- **验证安装**：`pnpm -v`

### 3. Git（推荐）
- **作用**：代码版本管理
- **下载地址**：https://git-scm.com/
- **验证安装**：`git --version`

### 4. VS Code（推荐）
- **作用**：代码编辑器
- **下载地址**：https://code.visualstudio.com/
- **推荐插件**：
  - ES7+ React/Redux/React-Native snippets
  - Prettier - Code formatter
  - TypeScript Vue Plugin (如果你也写 Vue)

### 5. 微信开发者工具（开发小程序必装）
- **作用**：预览和调试微信小程序
- **下载地址**：https://developers.weixin.qq.com/miniprogram/dev/devtools/download.html

### 6. PostgreSQL（后端数据库）
- **作用**：存储用户数据
- **下载地址**：https://www.postgresql.org/download/
- **或者用 Docker**：`docker run -d -p 5432:5432 -e POSTGRES_PASSWORD=123456 postgres:14`

---

## ✅ 环境检查清单

在终端运行以下命令，确保都能正常显示版本号：

```bash
node -v      # 应显示 v18.x.x 或更高
pnpm -v      # 应显示 8.x.x 或更高
git --version  # 应显示 git version x.x.x
```

全部 OK？那就可以开始了！ 🎉

---

## 🎯 这份提示词能帮你做什么？

### 如果你是 Taro 新手

| 你的困惑 | 这份提示词怎么帮你 |
|----------|-------------------|
| 不知道项目怎么组织 | 直接给你 Monorepo 最佳实践结构 |
| 不懂配置怎么写 | 所有 config 文件都是完整可用的 |
| 担心代码不规范 | 遵循分层架构 + TypeScript 严格模式 |
| 怕踩坑浪费时间 | 已经帮你填好了常见的坑 |

**核心价值**：**从第一天就按最佳实践写代码**，而不是先写错再改。

---

### 如果你是专业开发者

| 你的诉求 | 这份提示词怎么帮你 |
|----------|-------------------|
| 快速启动新项目 | 10 分钟生成完整脚手架，直接开始业务开发 |
| 不想重复造轮子 | 用户认证、API 封装、状态管理都写好了 |
| 保持技术选型一致 | 固定版本号，避免依赖冲突 |
| 需要可定制的模板 | 提示词结构清晰，随时按需修改 |

**核心价值**：**把重复的架构工作交给 AI**，你专注业务逻辑。

---

## 提示词设计的四个原则

这份提示词不是简单地"让 AI 帮我写代码"，而是遵循了四个设计原则：

### 1. 完整性约束
```
所有代码必须完整，不使用 `// ... 其他代码` 省略
```
普通提示词生成的代码经常是"示意性"的，这条约束让 AI 输出**可直接运行**的代码。

### 2. 版本锁定
```
Taro 3.6.32、React 18、TypeScript 5.x
```
明确版本号避免"我这能跑你那不能跑"的问题。

### 3. 多端兼容配置
```typescript
compiler: {
  type: 'webpack5',
  prebundle: { enable: false }  // 小程序必须
}
```
H5 和小程序的配置差异已经处理好了。

### 4. 分层架构模板
```
Routes → Controllers → Services → Models
```
后端代码遵循单一职责原则，新手也能写出可维护的代码。

---

## 🚀 快速体验

### 方式一：让 AI 帮你生成

把下面的提示词发给 **Claude / GPT-4 / Gemini**：

```
【粘贴 taro-monorepo-scaffold-prompt-v2.md 完整内容】
```

AI 会生成完整的项目代码，你只需要：
1. 创建对应目录和文件
2. 粘贴代码
3. `pnpm install && pnpm dev`

### 方式二：手动搭建（带命令）

```bash
# 1. 创建 Monorepo
mkdir my-app && cd my-app
pnpm init
echo "packages:\n  - 'packages/*'" > pnpm-workspace.yaml

# 2. 创建 Taro 前端
cd packages
npx @tarojs/cli@3.6.32 init taro-app
cd taro-app && pnpm add @nutui/nutui-react-taro zustand

# 3. 创建 Express 后端
cd ..
mkdir server && cd server
pnpm init
pnpm add express cors pg bcryptjs jsonwebtoken zod pino dotenv
pnpm add -D typescript tsx nodemon @types/node @types/express

# 4. 安装依赖
cd ../..
pnpm install
```

---

## 🏃 如何运行项目

项目创建好后，需要同时启动**后端**和**前端**。

### Step 1: 启动后端服务

```bash
# 打开终端 1
cd packages/server

# 创建环境变量文件（首次运行）
cp .env.example .env

# 启动开发服务器
pnpm dev
```

看到以下输出表示成功：
```
🚀 Server is running on http://localhost:3000
```

### Step 2: 启动 H5 网页版

```bash
# 打开终端 2
cd packages/taro-app

# 启动 H5 开发服务器
pnpm dev:h5
```

看到以下输出表示成功：
```
✔ Compiled successfully in xxx ms
```

打开浏览器访问 **http://localhost:10086** 即可看到页面。

### Step 3: 启动微信小程序

```bash
# 打开终端 3
cd packages/taro-app

# 编译小程序
pnpm dev:weapp
```

编译完成后，需要用**微信开发者工具**打开：

1. 打开微信开发者工具
2. 点击「+」或「导入项目」
3. 项目目录选择：`packages/taro-app/dist/weapp`
4. AppID 可以先用「测试号」
5. 点击「导入」

导入后就能在模拟器中看到小程序运行了！ 🎉

> 💡 **小白必知：热更新**
> 
> 使用 `pnpm dev:weapp` 启动后，修改代码会**自动重新编译**，微信开发者工具也会**自动刷新**，不需要每次手动删除 dist 文件夹！
> 
> **只有修改了 `config/index.ts` 配置文件或 `package.json` 依赖时**，才需要停止命令、删除 `dist/weapp`、重新运行 `dev:weapp`。

### 常用命令速查

| 命令 | 说明 |
|------|------|
| `pnpm dev:h5` | 启动 H5 网页版 |
| `pnpm dev:weapp` | 编译微信小程序 |
| `pnpm build:h5` | 构建 H5 生产版本 |
| `pnpm build:weapp` | 构建小程序生产版本 |

---

## ❓ 启动常见问题

### 问题 1：后端启动报 `ECONNREFUSED` 或数据库连接失败

**原因**：PostgreSQL 没启动，或连接信息不对

**解决**：
```bash
# 检查 PostgreSQL 是否运行
# Windows: 打开"服务"，找 postgresql 服务
# Mac: brew services list

# 检查 .env 文件中的数据库配置
DB_HOST=localhost
DB_PORT=5432
DB_NAME=my_app_db
DB_USER=postgres
DB_PASSWORD=你的密码
```

### 问题 2：端口被占用 `EADDRINUSE`

**原因**：3000 或 10086 端口已被其他程序使用

**解决**：
```bash
# Windows 查看占用端口的进程
netstat -ano | findstr :3000

# 杀掉进程（用上面查到的 PID）
taskkill /PID 进程号 /F

# 或者修改 .env 中的 PORT
```

### 问题 3：H5 请求 API 返回 404

**原因**：代理配置不对，或后端没启动

**解决**：
1. 确认后端已启动（终端显示 `Server is running`）
2. 检查 `config/dev.ts` 中的 proxy 配置
3. 确保请求路径以 `/api` 开头

### 问题 4：小程序报 `module 'prebundle/xxx' is not defined`

**原因**：Taro 的 prebundle 功能与 NutUI 不兼容

**解决**：
在 `config/index.ts` 中确保：
```typescript
compiler: {
  type: 'webpack5',
  prebundle: { enable: false }  // 必须是 false！
}
```
然后删除 `dist/weapp` 文件夹，重新运行 `pnpm dev:weapp`

### 问题 5：小程序报 `Not allowed by CORS`

**原因**：后端 CORS 配置没有放行小程序请求

**解决**：
确保 `server/src/middleware/cors.ts` 中开发环境放行所有请求：
```typescript
if (process.env.NODE_ENV !== 'production') {
  callback(null, true);
}
```

### 问题 6：`pnpm` 命令不存在

**原因**：没有全局安装 pnpm

**解决**：
```bash
npm install -g pnpm
```

### 问题 7：Windows PowerShell 报 "无法加载文件，因为在此系统上禁止运行脚本"

**原因**：PowerShell 执行策略限制

**解决**：以管理员身份运行 PowerShell，执行：
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

---

## ⚙️ 三个必须手动改的配置

即使用 AI 生成代码，也要**检查这三处**：

### 1. Prebundle 必须禁用
位置：`taro-app/config/index.ts`

```typescript
compiler: {
  type: 'webpack5',
  prebundle: { enable: false }  // ⚠️ 关键！
}
```

### 2. H5 开发代理
位置：`taro-app/config/dev.ts`

```typescript
h5: {
  devServer: {
    proxy: {
      '/api': {
        target: 'http://localhost:3000',
        changeOrigin: true
      }
    }
  }
}
```

### 3. CORS 开发模式
位置：`server/src/middleware/cors.ts`

```typescript
if (process.env.NODE_ENV !== 'production') {
  callback(null, true);  // 开发环境放行所有请求
}
```

---

## 📊 技术栈一览

| 层级 | 技术选型 |
|------|----------|
| **跨端框架** | Taro 3.6.32 |
| **前端框架** | React 18 + TypeScript |
| **UI 组件库** | NutUI React Taro |
| **状态管理** | Zustand |
| **后端框架** | Express 4.x |
| **数据库** | PostgreSQL |
| **运行时** | Node.js 18+ (tsx 直接运行 TS) |
| **包管理** | pnpm workspace |

---

## 🎯 适用场景

- ✅ 需要同时开发 **微信小程序 + H5 网页版** 的项目
- ✅ 全栈开发，前后端一体化管理
- ✅ 快速验证产品 MVP
- ✅ 学习 Taro + Node.js 全栈架构

---

## 获取完整提示词

### 方式一：GitHub（推荐）

提示词文件托管在 GitHub，可以随时获取最新版本：

**🔗 https://github.com/你的用户名/taro-fullstack-prompt**

> 如果你会用 Git，直接 clone 下来即可；不会也没关系，点进去后点击绿色的「Code」按钮，选择「Download ZIP」下载。

### 方式二：百度网盘

如果你无法访问 GitHub，我在**评论区置顶**放了百度网盘链接，直接下载即可。

---

### 怎么用？

1. 下载 `taro-monorepo-scaffold-prompt-v2.md` 文件
2. 复制文件里的全部内容
3. 粘贴给 **Claude / GPT-4 / Gemini** 等 AI
4. AI 会生成完整的项目代码
5. 按照本文的「如何运行项目」章节操作即可

---

## 💬 写在最后



## 🔗 相关资源

| 资源 | 链接 |
|------|------|
| **GitHub 仓库** | https://github.com/你的用户名/taro-fullstack-prompt |
| **百度网盘** | 见评论区置顶 |
| **Taro 官方文档** | https://taro-docs.jd.com |
| **NutUI React** | https://nutui.jd.com/react-taro |

---

💡 **如果这篇文章对你有帮助，请点赞、收藏、转发，让更多人看到！**

有任何问题，欢迎留言交流，我会尽力解答 ✨
```

---

## 🤖 文档二：AI Prompt 提示词

**使用方法：复制下面代码块的全部内容，粘贴给 Claude / GPT-4 / Gemini 等 AI**

```markdown
# Taro 一码多端 Monorepo 全栈项目脚手架生成提示词（改进版 v2）

你是一名资深全栈架构师。请为我生成一个**完整可运行**的 Monorepo 全栈项目脚手架，严格遵循工程最佳实践。

## 核心要求
- 所有代码必须完整、可复制、可直接运行
- 使用 **Taro 3.6.x** 实现一套代码同时支持 Web（H5）和微信小程序
- 后端必须采用分层架构：Routes → Controllers → Services → Models
- 前后端通过 API 通信，H5 端使用代理，小程序直接请求
- 使用 pnpm workspace 管理 Monorepo
- **H5 端使用标准 CSS 响应式设计，禁用 pxtransform**

---

## 技术栈规范

### 1. Monorepo 结构
- **工具**：pnpm workspace
- **结构**：
  ```
  /
  ├── packages/taro-app   # Taro 跨端应用（Web + 小程序）
  ├── packages/server     # 后端服务
  ├── package.json        # workspace root
  └── pnpm-workspace.yaml
  ```

---

### 2. 前端技术栈 (packages/taro-app)

#### 核心技术
| 技术 | 版本/说明 |
|------|----------|
| **框架** | Taro 3.6.32 + React 18 + TypeScript |
| **UI 组件** | @nutui/nutui-react-taro@^2.3.0（注意：不要显式安装 @nutui/icons-react-taro，它会作为内部依赖自动安装；**Button 组件需使用 Taro 原生组件，见下方注意事项**） |
| **状态管理** | Zustand 4.x |
| **HTTP 请求** | Taro.request 封装 |
| **CSS 预处理** | Sass |
| **编译目标** | H5 (Web) + 微信小程序 (weapp) |

#### 必须包含的文件

**配置文件**：
- `package.json` - 依赖和脚本
- `tsconfig.json` - TypeScript 配置
- `babel.config.js` - Babel 配置（使用 babel-preset-taro）
- `.env.development` - 开发环境变量
- `.env.production` - 生产环境变量
- `project.config.json` - 微信小程序项目配置

**Taro 配置**：
- `config/index.ts` - Taro 主配置文件
- `config/dev.ts` - 开发环境配置（**必须包含 H5 proxy 配置**）
- `config/prod.ts` - 生产环境配置

**应用代码**：
- `src/app.config.ts` - 应用配置（页面路由，**登录页为默认启动页，无 tabBar**）
- `src/app.tsx` - 应用入口
- `src/app.scss` - 全局样式（**响应式设计，使用 CSS 变量和媒体查询**）
- `src/index.html` - H5 入口模板（**无移动端缩放脚本**）

**页面**：
- `src/pages/login/index.tsx` - 登录页（**默认启动页**）
- `src/pages/login/index.scss`
- `src/pages/index/index.tsx` - 首页
- `src/pages/index/index.scss`
- `src/pages/profile/index.tsx` - 个人中心页
- `src/pages/profile/index.scss`
- `src/pages/change-password/index.tsx` - 修改密码页
- `src/pages/change-password/index.scss`

**API 层**：
- `src/api/config.ts` - API 配置（根据 TARO_ENV 设置不同 baseURL）
- `src/api/http.ts` - Taro.request 封装（含请求/响应拦截器）
- `src/api/modules/user.ts` - 用户相关 API
- `src/api/index.ts` - API 模块统一导出

**公共模块**：
- `src/components/Loading/index.tsx` - 加载组件
- `src/components/EmptyState/index.tsx` - 空状态组件
- `src/utils/storage.ts` - 存储工具
- `src/utils/toast.ts` - 提示工具
- `src/store/user.ts` - 用户状态（Zustand）
- `src/store/index.ts` - Store 统一导出
- `src/types/index.ts` - 全局类型定义

#### 关键配置要求

##### package.json 关键配置
```json
{
  "browserslist": [
    "Chrome >= 67",
    "Safari >= 12",
    "Firefox >= 68",
    "Edge >= 79",
    "iOS >= 12",
    "Android >= 67"
  ],
  "devDependencies": {
    "@babel/core": "^7.23.2",
    "@pmmmwh/react-refresh-webpack-plugin": "^0.5.11",
    "@tarojs/cli": "3.6.32",
    "@tarojs/taro-loader": "3.6.32",
    "@tarojs/webpack5-runner": "3.6.32",
    "@types/react": "^18.2.37",
    "@types/webpack-env": "^1.18.3",
    "babel-preset-taro": "3.6.32",
    "postcss": "^8.4.31",
    "react-refresh": "^0.14.0",
    "sass": "^1.69.5",
    "typescript": "^5.2.2",
    "webpack": "^5.89.0"
  }
}
```

##### H5 开发模式 Proxy 配置（config/dev.ts）
```typescript
export default {
  h5: {
    devServer: {
      port: 10086,
      host: '0.0.0.0',
      proxy: {
        '/api': {
          target: 'http://localhost:3000',
          changeOrigin: true,
          pathRewrite: { '^/api': '/api' }
        }
      }
    }
  }
};
```

##### 编译器配置（config/index.ts - 禁用 prebundle）
> ⚠️ **重要**：Taro 3.6+ 必须在 `compiler` 对象中禁用 prebundle，否则小程序端会报 `module 'prebundle/xxx.wxss.js' is not defined` 错误。

```typescript
compiler: {
  type: 'webpack5',
  prebundle: {
    enable: false  // 禁用 prebundle，解决 NutUI icons CSS 模块加载错误
  }
},
```

##### H5 配置（config/index.ts 关键部分）
```typescript
h5: {
  publicPath: '/',
  staticDirectory: 'static',
  postcss: {
    autoprefixer: {
      enable: true,
      config: {}
    },
    // 禁用 H5 的 pxtransform，使用原生 CSS 像素实现响应式
    pxtransform: {
      enable: false
    },
    cssModules: {
      enable: false,
      config: {
        namingPattern: 'module',
        generateScopedName: '[name]__[local]___[hash:base64:5]'
      }
    }
  },
  esnextModules: ['@nutui/nutui-react-taro'],
  // 忽略 Taro 内部模块的警告
  webpackChain(chain) {
    chain.merge({
      ignoreWarnings: [
        /You don't need `webpackExports`/,
        /The generated code contains 'async\/await'/,
        /target environment does not appear to support/
      ]
    });
  }
}
```

##### index.html（无移动端缩放脚本）
```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
  <meta name="description" content="Taro Cross-Platform Application">
  <title>My App</title>
  <style>
    *, *::before, *::after { box-sizing: border-box; }
    html, body { margin: 0; padding: 0; width: 100%; min-height: 100%; font-size: 16px; }
    #app { width: 100%; min-height: 100vh; }
  </style>
</head>
<body>
  <div id="app"></div>
</body>
</html>
```

##### app.config.ts（登录页为默认启动页，无 tabBar）
```typescript
export default defineAppConfig({
  pages: [
    'pages/login/index',      // 登录页设为默认启动页
    'pages/index/index',
    'pages/profile/index',
    'pages/change-password/index'
  ],
  window: {
    backgroundTextStyle: 'light',
    navigationBarBackgroundColor: '#fff',
    navigationBarTitleText: 'My App',
    navigationBarTextStyle: 'black'
  }
});
```

##### project.config.json（微信小程序项目配置）
>
