# 记宝盒 - 资产物品管理小程序（jbh-ucmao-mp）

## 项目介绍
记宝盒是一款专为个人和家庭设计的资产物品管理微信小程序，帮助用户轻松记录、管理和统计各类资产物品的购买信息、使用情况和退役状态。

> 本仓库仅包含前端（小程序）代码。后端 API 接口实现请参考 [后端仓库链接](https://github.com/ucmao/jbh-ucmao-backend)

## 📱 立即体验与总览 ✨

欢迎扫码体验本项目的实际功能和效果。

| 扫码体验正式版 | 后端服务仓库 |
| :---: | :---: |
| ![记宝盒太阳码](qr_code.jpg) | 🚀 [记宝盒后端服务 (Python)](https://github.com/ucmao/jbh-ucmao-backend) |

## 功能特性

### 核心功能
- ✅ **资产记录**：记录资产名称、分类、购买价格、购买日期等详细信息
- ✅ **资产管理**：支持添加、编辑、删除资产信息
- ✅ **分类管理**：多种资产分类（数码、服饰、美妆、母婴等）
- ✅ **使用统计**：支持记录预计使用次数或日均价格
- ✅ **退役管理**：记录资产退役信息（退役日期、退役价格）
- ✅ **数据统计**：查看资产统计报表
- ✅ **资产收藏**：收藏重要资产
- ✅ **分享功能**：分享资产信息给好友

### 辅助功能
- 📱 **响应式设计**：适配各种屏幕尺寸
- 🔍 **搜索功能**：快速查找资产
- 📊 **数据可视化**：直观的统计图表
- 💾 **本地缓存**：优化用户体验

## 技术栈

- **框架**：微信小程序原生开发
- **语言**：JavaScript
- **UI组件**：微信小程序原生组件
- **数据请求**：wx.request
- **存储**：微信小程序本地存储（wx.setStorageSync）
- **版本控制**：Git

## 项目结构

```
├── images/                 # 静态图片资源
├── pages/                  # 页面文件
│   ├── add/               # 添加资产页面
│   ├── edit/              # 编辑资产页面
│   ├── index/             # 首页（资产列表）
│   ├── select-icon/       # 选择图标页面
│   ├── statistics/        # 统计页面
│   └── user/              # 用户页面
├── utils/                 # 工具函数
│   ├── config.js          # 配置文件
│   └── util.js            # 通用工具函数
├── .gitignore            # Git忽略文件
├── app.js                # 小程序入口文件
├── app.json              # 全局配置文件
├── app.wxss              # 全局样式文件
├── project.config.json   # 项目配置文件
└── sitemap.json          # 微信搜索配置
```

## 快速开始

### 环境要求
- 微信开发者工具
- 微信小程序账号

### 安装与运行

1. **克隆项目**
   ```bash
   git clone https://github.com/ucmao/jbh_ucmao_mp.git
   ```

2. **导入项目**
   - 打开微信开发者工具
   - 选择「导入项目」
   - 填写项目信息，选择克隆的项目目录
   - 点击「导入」

3. **配置项目**
   - 打开 `utils/config.js` 文件
   - 根据需要修改配置项（如域名、应用名称等）

4. **运行项目**
   - 在微信开发者工具中点击「编译」
   - 使用微信扫码预览

## 配置说明

### 配置文件使用

1. 复制 `utils/config.example.js` 文件并重命名为 `utils/config.js`
2. 根据你的实际情况修改 `config.js` 中的配置项

### 配置项说明

配置文件主要包含以下配置项：

### 域名配置
```javascript
domain: 'https://your-domain.com'  // API请求域名
```

### 应用名称配置
```javascript
appName: {
  full: '你的应用名称',             // 应用全称
  short: '应用简称',            // 应用简称
  description: '你的应用描述！'  // 应用描述
}
```

### API路径配置
```javascript
apiPath: {
  login: '/api/login',               // 登录接口
  userItems: '/api/items/user/',     // 用户资产列表接口
  itemDetail: '/api/items/item/',    // 资产详情接口
  categories: '/api/items/categories',  // 分类接口
  addItem: '/api/items/add_item',    // 添加资产接口
  reportItems: '/api/report/report-items/'  // 统计报表接口
}
```

### 静态资源配置
```javascript
staticPath: {
  shareImage: '/static/default/share-image.jpg'  // 分享图片路径
}
```

## 页面说明

### 1. 首页（index）
- 展示用户的资产列表
- 支持资产搜索和筛选
- 快速进入资产详情、编辑或删除

### 2. 添加资产（add）
- 填写资产基本信息
- 选择资产分类和图标
- 设置购买价格和日期
- 配置使用统计（使用次数或日均价格）
- 设置退役信息（可选）

### 3. 编辑资产（edit）
- 修改现有资产信息
- 支持部分或全部字段修改

### 4. 统计页面（statistics）
- 查看资产统计报表
- 数据可视化展示

### 5. 用户页面（user）
- 用户信息管理
- 应用设置
- 关于我们

## 开发说明

### 代码规范
- 使用微信小程序原生开发规范
- 函数命名使用驼峰命名法
- 页面和组件命名清晰明了
- 注释完整，说明功能和参数

### 工具函数
通用工具函数位于 `utils/util.js`，包含：
- `formatTime()`：格式化时间
- `formatDate()`：格式化日期
- `regex`：正则表达式验证规则

### 网络请求
- 使用微信小程序原生 `wx.request` 进行网络请求
- 所有API请求通过 `config.js` 中的配置进行管理
- 请求超时时间为10秒

## 贡献

欢迎提交 Issue 和 Pull Request！

### 提交规范

- 提交代码前请确保通过语法检查
- 提交信息请使用清晰的描述，如：`fix: 修复数据库连接错误`

## 许可证

本项目采用 MIT License - 查看 [LICENSE](LICENSE) 文件了解详情

## 联系方式

如果您有任何问题或建议，请通过以下方式联系我们：
- 邮箱：leoucmao@gmail.com
- GitHub：https://github.com/ucmao

---

**记宝盒 - 让资产管理更简单！** 📦💼✨