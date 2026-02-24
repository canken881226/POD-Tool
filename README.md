# POD智能开发工具 - 部署说明

## 文件结构
```
你的GitHub仓库/
├── index.html          ← 工具主体（很少需要改）
├── config.js           ← ⭐ API Key配置（改这里）
├── data/
│   └── pod_data.js     ← ⭐ 所有数据（关键词库/元素库/侵权库等）
└── README.md           ← 本说明
```

---

## 第一次部署（约10分钟）

### 第1步：注册GitHub账号
1. 打开 https://github.com
2. 点击 Sign up，用邮箱注册
3. 验证邮箱

### 第2步：创建仓库
1. 登录后，点击右上角 **+** → **New repository**
2. Repository name 填：`pod-tool`
3. 选择 **Public**（必须选Public才能免费部署）
4. 点击 **Create repository**

### 第3步：上传文件
1. 在新建的仓库页面，点击 **uploading an existing file**
2. 把这个文件夹里的所有文件拖进去：
   - index.html
   - config.js
   - data/ 文件夹（含pod_data.js）
3. 点击 **Commit changes**

### 第4步：开启GitHub Pages
1. 点击仓库顶部 **Settings**
2. 左侧找到 **Pages**
3. Source 选择 **Deploy from a branch**
4. Branch 选择 **main**，文件夹选 **/ (root)**
5. 点击 **Save**
6. 等约1分钟，页面会显示网址：`https://你的用户名.github.io/pod-tool`

### 第5步：填入API Key
1. 打开仓库里的 **config.js** 文件
2. 点击右上角铅笔图标（编辑）
3. 把 `YOUR_ANTHROPIC_API_KEY_HERE` 替换成你的真实API Key
4. 点击 **Commit changes**

**完成！** 把网址发给同事，打开就能用。

---

## 日常更新操作

### 更新关键词库 / 元素库 / 侵权数据
1. 打开GitHub仓库
2. 点击 `data/pod_data.js`
3. 点击铅笔图标编辑
4. 修改对应数据
5. 点击 **Commit changes**
6. **同事刷新浏览器即可看到最新数据**（约1分钟生效）

### 更新工具本身（功能升级）
1. 把新版 `index.html` 上传到仓库（同名覆盖）
2. 同事刷新浏览器即可

### 更换API Key
1. 打开 `config.js`
2. 修改 apiKey 的值
3. Commit → 同事刷新即可

---

## 常见问题

**Q：打开网址是空白页？**
A：等1-2分钟让GitHub Pages生效，再刷新

**Q：API调用失败？**
A：检查config.js里的apiKey是否正确，注意前后不要有多余空格

**Q：同事打开网址看到旧数据？**
A：让同事按 Ctrl+Shift+R 强制刷新（清除缓存）

**Q：能不能给不同人看不同数据？**
A：目前是所有人共享同一份数据，适合小团队

---

## 数据文件说明（data/pod_data.js）

| 数据块 | 说明 | 更新频率 |
|--------|------|----------|
| SYSTEM_DATA | 节假日、品类等基础数据 | 低 |
| ELEMENT_LIBRARY | 元素库（男/女/中性） | 中 |
| MJ_STYLES | MJ咒语风格库 | 低 |
| KW_DB | 关键词库（童装/家居分类目） | 高 |
| THEME_ELEMENTS | 主题元素（各节日热卖元素） | 中 |
| DEFAULT_CP_DB | 侵权案例数据库 | 高 |
| CROSS_REF | 跨类目参考 | 低 |
| CAT_COLORS | 品类颜色主题 | 极低 |
