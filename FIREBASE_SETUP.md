# Firebase 配置指南

## 📋 配置步骤

### 1. 创建 Firebase 项目

1. 访问 [Firebase Console](https://console.firebase.google.com/)
2. 点击"添加项目"
3. 输入项目名称（如：gift-selection-system）
4. 按提示完成项目创建

### 2. 启用 Realtime Database

1. 在左侧菜单选择"构建" → "Realtime Database"
2. 点击"创建数据库"
3. 选择数据库位置（推荐：asia-southeast1）
4. 选择"以测试模式启动"（或使用下面的规则）

### 3. 配置数据库规则

在"规则"标签页，设置以下规则：

**开发/测试环境**（允许所有读写）：
```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```

**生产环境**（推荐使用更安全的规则）：
```json
{
  "rules": {
    "gifts": {
      ".read": true,
      ".write": true
    },
    "records": {
      ".read": true,
      ".write": true
    }
  }
}
```

### 4. 获取配置信息

1. 点击项目设置（齿轮图标）
2. 在"常规"选项卡下找到"您的应用"
3. 选择 Web 应用（</> 图标）
4. 注册应用并复制配置代码

示例配置：
```javascript
const firebaseConfig = {
  apiKey: "AIzaSyXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX",
  authDomain: "your-project.firebaseapp.com",
  databaseURL: "https://your-project-default-rtdb.firebaseio.com",
  projectId: "your-project",
  storageBucket: "your-project.appspot.com",
  messagingSenderId: "123456789012",
  appId: "1:123456789012:web:abcdef123456"
};
```

### 5. 更新 index.html

在 `index.html` 中找到 Firebase 配置部分（约第 505 行）：

```javascript
const firebaseConfig = {
    apiKey: "YOUR_API_KEY",           // 替换这里
    authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
    databaseURL: "https://YOUR_PROJECT_ID-default-rtdb.firebaseio.com",
    projectId: "YOUR_PROJECT_ID",
    storageBucket: "YOUR_PROJECT_ID.appspot.com",
    messagingSenderId: "YOUR_SENDER_ID",
    appId: "YOUR_APP_ID"
};
```

将 `YOUR_API_KEY`、`YOUR_PROJECT_ID` 等替换为您的实际配置。

### 6. 修改系统密码

在 `index.html` 中找到密码配置（约第 520 行）：

```javascript
const SYSTEM_PASSWORD = "xrs2024";  // 修改为您的密码
```

### 7. 提交并推送更新

```bash
cd "/Users/blueberry/Desktop/礼物选择系统"
git add index.html
git commit -m "配置Firebase"
git push origin main
```

### 8. 等待部署

GitHub Pages 会自动重新部署，大约需要 1-2 分钟。

## 🔍 测试验证

1. 访问：https://blueberryyou.github.io/gift-selection-system/
2. 输入密码登录
3. 在一个设备上选择礼物
4. 在另一个设备上刷新页面，应该能看到实时更新

## ⚠️ 注意事项

1. **不要在公开仓库中提交包含 Firebase 配置的代码**，因为会暴露 API Key
2. 如需公开代码，建议：
   - 使用环境变量
   - 配置 Firebase 安全规则
   - 启用 App Check
3. **定期备份数据**：在管理后台导出记录
4. **监控使用量**：Firebase 免费套餐有限额，注意监控

## 🆘 常见问题

### 问题1：数据不同步
- 检查 Firebase 控制台是否能看到数据
- 检查浏览器控制台是否有错误
- 确认数据库规则允许读写

### 问题2：无法登录
- 检查密码是否正确
- 清除浏览器缓存
- 使用无痕模式测试

### 问题3：截图上传失败
- 检查图片大小（建议 < 1MB）
- 检查 Firebase 配置是否正确
- Base64 编码可能会增大数据大小

## 📞 需要帮助？

如有问题，请检查：
1. Firebase Console 的实时数据库数据
2. 浏览器开发者工具的 Console 和 Network 面板
3. GitHub Pages 部署状态
