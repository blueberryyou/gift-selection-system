# 🎁 达标奖励礼物选择系统

一个基于 Firebase 实时数据库的礼物选择系统，支持多设备实时同步、密码保护和达标截图上传。

## ✨ 功能特点

- 🔐 **密码保护**：系统访问需要输入密码（默认密码：`xrs2024`）
- 📸 **截图上传**：选择礼物时需要上传达标截图作为凭证
- 🔄 **实时同步**：基于 Firebase 的多设备实时数据同步
- 📊 **库存管理**：实时显示礼物库存，自动更新
- 📝 **记录追踪**：完整记录每次选择的详细信息
- 📱 **响应式设计**：支持手机、平板、电脑等各种设备
- 🎨 **渐变标题**：橙色到蓝色的渐变效果

## 🚀 部署说明

### 1. 配置 Firebase

1. 访问 [Firebase Console](https://console.firebase.google.com/)
2. 创建新项目或选择现有项目
3. 在项目设置中找到 Firebase 配置信息
4. 启用 Realtime Database
5. 设置数据库规则（开发环境可以使用以下规则）：

```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```

**注意**：生产环境请配置更严格的安全规则。

### 2. 修改配置

在 `index.html` 中找到 Firebase 配置部分，替换为您的实际配置：

```javascript
const firebaseConfig = {
    apiKey: "YOUR_API_KEY",
    authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
    databaseURL: "https://YOUR_PROJECT_ID-default-rtdb.firebaseio.com",
    projectId: "YOUR_PROJECT_ID",
    storageBucket: "YOUR_PROJECT_ID.appspot.com",
    messagingSenderId: "YOUR_SENDER_ID",
    appId: "YOUR_APP_ID"
};
```

### 3. 修改密码

在代码中找到并修改系统密码：

```javascript
const SYSTEM_PASSWORD = "xrs2024"; // 修改为您的密码
```

### 4. 部署到 GitHub Pages

1. 将项目推送到 GitHub 仓库
2. 在仓库设置中启用 GitHub Pages
3. 选择主分支作为发布源
4. 访问生成的在线链接

## 📦 礼物清单

系统包含以下 11 种礼物，每种礼物都有对应的库存数量：

1. 大疆 osmo mobile se om 手持云台 - 20件
2. 原始人黑胶天幕 - 40件
3. 九阳即热饮水机 - 3件
4. gree格力烘干机 - 30件
5. 妙界R3至尊版肩颈按摩仪 - 30件
6. 探险者户外折叠桌蛋卷桌便携式露营桌椅 - 30件
7. DTA行李箱20英寸 前开+水杯架+USB充电 - 25件
8. Bincoo手冲咖啡壶套装 - 25件
9. 马歇尔（Marshall）MAJOR IV耳机头戴 - 22件
10. 小熊（Bear）电火锅火锅专用锅电煮锅 - 22件
11. 萨伽（SAGA）吉他sf600 - 22件

## 💡 使用说明

### 选择礼物

1. 输入系统密码登录
2. 在"选择礼物"页面浏览可用礼物
3. 点击"选择此礼物"按钮
4. 填写个人信息（姓名、达标时间）
5. 上传达标截图
6. 确认提交

### 查看记录

在"选择记录"页面可以：
- 查看所有选择记录
- 点击截图缩略图查看大图
- 导出记录为 Excel 文件

### 管理后台

管理员可以在"管理后台"页面：
- 查看实时库存状态
- 重置库存数量
- 清空选择记录
- 重置全部数据

## 🔒 安全建议

1. **修改默认密码**：部署前请务必修改默认密码
2. **配置 Firebase 规则**：在生产环境使用更严格的数据库访问规则
3. **HTTPS 部署**：确保网站通过 HTTPS 访问
4. **定期备份**：定期导出和备份选择记录

## 📱 兼容性

- ✅ Chrome / Edge（推荐）
- ✅ Safari
- ✅ Firefox
- ✅ 移动端浏览器

## 🛠️ 技术栈

- HTML5 + CSS3
- JavaScript (ES6+)
- Firebase Realtime Database
- 响应式设计

## 📝 License

MIT License
