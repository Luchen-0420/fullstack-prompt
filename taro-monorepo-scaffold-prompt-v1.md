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

##### 响应式全局样式（app.scss）
```scss
/* 颜色和间距变量 */
:root {
  --primary-color: #fa2c19;
  --text-color: #333333;
  --text-secondary: #666666;
  --bg-color: #f5f5f5;
  --white: #ffffff;
  --spacing-md: 16px;
  --spacing-lg: 24px;
  --font-size-base: 16px;
  --radius-lg: 12px;
}

/* 基础样式 */
page {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  font-size: var(--font-size-base);
  color: var(--text-color);
  background: var(--bg-color);
}

.container {
  min-height: 100vh;
  padding: var(--spacing-md);
  width: 100%;
}

.card {
  background: var(--white);
  border-radius: var(--radius-lg);
  padding: var(--spacing-md);
  margin-bottom: var(--spacing-md);
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
}

/* 平板端 (768px+) */
@media screen and (min-width: 768px) {
  .container { max-width: 720px; margin: 0 auto; padding: var(--spacing-lg); }
}

/* 桌面端 (1024px+) */
@media screen and (min-width: 1024px) {
  .container { max-width: 960px; }
  .card:hover { box-shadow: 0 6px 24px rgba(0, 0, 0, 0.12); }
}

/* 大屏 (1280px+) */
@media screen and (min-width: 1280px) {
  .container { max-width: 1200px; }
}
```

##### 多端 API baseURL 处理（src/api/config.ts）
```typescript
const getBaseURL = (): string => {
  const env = process.env.TARO_ENV;
  
  if (env === 'h5') {
    return process.env.NODE_ENV === 'development' ? '/api' : 'https://your-domain.com/api';
  }
  
  return process.env.NODE_ENV === 'development' 
    ? 'http://localhost:3000/api'
    : 'https://your-domain.com/api';
};

export const API_BASE_URL = getBaseURL();
```

---

### 3. 后端技术栈 (packages/server)

#### 核心技术
| 技术 | 版本/说明 |
|------|----------|
| **运行时** | Node.js 18+ + TypeScript 5.x |
| **框架** | Express 4.x |
| **执行工具** | tsx（无需编译直接运行 TS） |
| **数据库** | PostgreSQL 14+ |
| **数据库驱动** | pg (node-postgres) |
| **环境变量** | dotenv |
| **日志** | pino + pino-pretty |
| **验证** | zod |
| **密码加密** | bcryptjs |
| **JWT** | jsonwebtoken |

#### 分层架构目录结构

```
packages/server/
├── src/
│   ├── index.ts              # 入口文件
│   ├── app.ts                # Express 应用配置
│   ├── routes/
│   │   ├── index.ts
│   │   └── user.routes.ts
│   ├── controllers/
│   │   └── user.controller.ts
│   ├── services/
│   │   └── user.service.ts
│   ├── models/
│   │   └── user.model.ts
│   ├── db/
│   │   ├── client.ts
│   │   └── schema.sql
│   ├── middleware/
│   │   ├── error.ts
│   │   ├── cors.ts
│   │   ├── auth.ts
│   │   └── validate.ts
│   └── utils/
│       ├── logger.ts
│       ├── response.ts
│       └── jwt.ts
├── package.json
├── tsconfig.json
├── .env.example
└── nodemon.json
```

#### 业务模块

**user**（用户管理）：
- POST `/api/users/register` - 用户注册
- POST `/api/users/login` - 用户登录
- GET `/api/users/profile` - 获取当前用户信息（需认证）
- PUT `/api/users/profile` - 更新用户信息（需认证）
- PUT `/api/users/password` - 修改密码（需认证）

#### 配置文件

**.env.example**：
```env
# Server
PORT=3000
NODE_ENV=development

# Database
DB_HOST=localhost
DB_PORT=5432
DB_NAME=my_app_db
DB_USER=postgres
DB_PASSWORD=password

# JWT
JWT_SECRET=your-super-secret-key-change-in-production
JWT_EXPIRES_IN=7d

# CORS
CORS_ORIGIN=http://localhost:10086
```

##### 数据库连接池（使用分离变量）
```typescript
export const pool = new Pool({
  host: process.env.DB_HOST || 'localhost',
  port: parseInt(process.env.DB_PORT || '5432', 10),
  database: process.env.DB_NAME || 'my_app_db',
  user: process.env.DB_USER || 'postgres',
  password: process.env.DB_PASSWORD || 'password',
  max: 20,
  idleTimeoutMillis: 30000,
  connectionTimeoutMillis: 2000,
});
```

##### CORS 中间件（开发环境允许所有来源）
> ⚠️ **重要**：小程序端请求的 origin 与 H5 不同，开发环境需允许所有来源，否则会报 "Not allowed by CORS" 错误。

```typescript
// src/middleware/cors.ts
import cors from 'cors';

const isDevelopment = process.env.NODE_ENV !== 'production';

const corsOptions: cors.CorsOptions = {
  origin: (origin, callback) => {
    // 开发环境允许所有来源（方便小程序和 H5 调试）
    if (isDevelopment) {
      callback(null, true);
      return;
    }
    
    // 生产环境：允许无 origin 的请求（小程序、curl）
    if (!origin) {
      callback(null, true);
      return;
    }
    
    const allowedOrigins = (process.env.CORS_ORIGIN || '').split(',').map(o => o.trim());
    if (allowedOrigins.includes(origin) || allowedOrigins.includes('*')) {
      callback(null, true);
    } else {
      callback(new Error('Not allowed by CORS'));
    }
  },
  credentials: true,
  methods: ['GET', 'POST', 'PUT', 'DELETE', 'PATCH', 'OPTIONS'],
  allowedHeaders: ['Content-Type', 'Authorization'],
};

export const corsMiddleware = cors(corsOptions);
```

---

## 关键约束和最佳实践

### 代码规范
- 所有 TypeScript 必须开启 `strict` 模式
- 统一使用 async/await
- 错误处理必须完整（try-catch + 统一错误中间件）
- 前端组件使用函数式组件 + Hooks

### TSX 泛型语法
- 在 `.tsx` 文件中，单个泛型参数的箭头函数需要添加尾随逗号：
  ```typescript
  // ❌ 错误
  const fn = <T>(arg: T) => arg;
  
  // ✅ 正确
  const fn = <T,>(arg: T) => arg;
  ```

### H5 响应式设计
- 禁用 pxtransform，使用原生 CSS 像素（px）
- 使用 CSS 变量实现主题一致性
- 使用媒体查询断点：768px（平板）、1024px（桌面）、1280px（大屏）
- 页面样式文件包含响应式媒体查询

### API 设计
- RESTful 风格
- 统一响应格式：`{ code: number, data: T | null, message: string }`
- HTTP 状态码：200/201/400/401/403/404/500

### 多端兼容性
- 使用 `process.env.TARO_ENV` 判断当前运行环境
- 避免使用 Web 独有 API（如 window、document）
- 小程序端使用 rpx，H5 端使用 px + 媒体查询

### 路由跳转注意事项
> ⚠️ **重要**：由于本脚手架配置无 tabBar，**禁止使用 `Taro.switchTab`**，否则小程序端会报错 `switchTab:fail can not switch to no-tabBar page`。

**路由 API 使用规范**：
| 场景 | 使用的 API |
|------|-----------|
| 普通页面跳转（可返回） | `Taro.navigateTo({ url: '/pages/xxx/index' })` |
| 登录成功后跳转首页（不可返回） | `Taro.redirectTo({ url: '/pages/index/index' })` |
| 返回上一页 | `Taro.navigateBack()` |

### Button 组件注意事项
> ⚠️ **重要**：NutUI 的 Button 组件在小程序端存在兼容性问题（`block` 属性无效、文字不显示等），**必须使用 Taro 原生 Button 组件**。

**解决方案**：使用 Taro 原生 Button 组件（`@tarojs/components`），样式手动定义：
```tsx
import { Button } from '@tarojs/components';
// 不要使用 block 属性，通过 CSS width: 100% 实现全宽
<Button className="submit-btn" type="primary" loading={loading} onClick={handleSubmit}>登录</Button>
```

**按钮样式示例**（SCSS）：
```scss
.submit-btn {
    width: 100% !important;
    margin-top: 24px;
    height: 48px !important;
    line-height: 48px !important;
    border-radius: 24px !important;
    font-size: 16px !important;
    background: linear-gradient(135deg, #fa2c19 0%, #ff6b35 100%) !important;
    color: #fff !important;
    border: none !important;
}
```

### 安全性
- 密码使用 bcryptjs hash 存储
- JWT 密钥使用环境变量
- 使用参数化查询防止 SQL 注入
- CORS **开发环境允许所有来源**（方便小程序和 H5 调试），生产环境仅允许配置的域名

---

## 输出要求总结

1. **所有代码必须完整**，不使用 `// ... 其他代码` 省略
2. **必须可直接运行**，复制粘贴即可使用
3. **配置文件必须完整**，包含所有必要字段
4. **明确版本号**，避免依赖冲突
5. **注释清晰**，关键逻辑处添加注释
6. **遵循分层架构**，各层职责清晰
7. **H5 使用响应式设计**，禁用 pxtransform
8. **登录页为默认启动页**，无 tabBar

请开始生成，确保输出内容完整、规范、可执行。
