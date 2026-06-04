# 多人协作指南

## 项目信息

- **项目名称**: Verix Roadshow (neex-bot)
- **域名**: neex.bot
- **仓库**: https://github.com/[your-username]/neex-bot

## 协作流程

### 1. 首次设置

```bash
# 克隆仓库
git clone https://github.com/[your-username]/neex-bot.git
cd neex-bot
```

### 2. 编辑文件

- **主页面**: 直接编辑 `index.html`
- 使用任何文本编辑器或 HTML 编辑器

### 3. 提交更改

```bash
# 查看修改
git status

# 添加修改的文件
git add index.html

# 提交更改（写清楚改了什么）
git commit -m "更新 hero 区域文案"

# 推送到 GitHub
git push origin master
```

### 4. 推荐协作方式：使用分支

```bash
# 创建新分支
git checkout -b update-intro-section

# 编辑文件
# ...

# 提交并推送
git add .
git commit -m "更新介绍部分的文案和样式"
git push origin update-intro-section

# 在 GitHub 上创建 Pull Request
# 其他人可以 Review 后再合并
```

## 自动部署

推送到 `master` 分支后，GitHub Actions 会自动：
1. 构建网站
2. 部署到 GitHub Pages

大约 1-2 分钟后访问 **neex.bot** 即可看到更新。

## 团队成员协作

### 邀请协作者

**仓库管理员**操作：

1. 进入仓库 Settings → Collaborators
2. 添加团队成员的 GitHub 用户名
3. 确认邀请

### Fork + PR 流程（开放给任何人）

如果不想直接添加协作者，可以让其他人：
1. Fork 仓库
2. 在自己的 Fork 中修改
3. 提交 Pull Request
4. 管理员 Review 后合并

## 本地预览

```bash
# 方法 1: 直接用浏览器打开
open index.html

# 方法 2: 使用本地服务器
npx serve .
# 访问 http://localhost:3000
```

## 文件结构

```
neex-bot/
├── index.html          ← 主页面（Verix Roadshow）
├── README.md           ← 项目说明
├── COLLABORATION.md    ← 本协作指南
└── .github/
    └── workflows/
        └── deploy.yml  ← 自动部署配置
```

## 常见问题

**Q: 两个人同时编辑怎么办？**
A: 使用分支！每个人创建自己的分支，完成后提交 PR 合并。

**Q: 如何避免冲突？**
A: 在开始修改前先 `git pull` 确保代码是最新的。

**Q: 修改错了怎么办？**
A: 使用 `git checkout -- index.html` 恢复文件，或 `git reset` 撤销提交。
