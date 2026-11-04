# 偶像行程网站 · 部署说明（全免费，只用 GitHub）

## 文件说明
- `index.html`：访客页面（行程 + 自动轮播），任何人有链接即可访问
- `admin.html`：管理员页面（Only for 管理员，需要密码）
- `data.json`：所有行程和轮播内容（后台自动更新，不用手动改）
- `uploads/`：后台上传的图片/视频（自动生成）

## 一次性部署（约 10 分钟）

### 1. 创建仓库并上传文件
1. 注册 GitHub 账号（免费）：https://github.com
2. 点右上角 `+` → `New repository`，名字随意（例如 `idol-schedule`），选 **Public**（免费 Pages 要求公开），创建。
3. 点 `uploading an existing file`，把 `index.html`、`admin.html`、`data.json` 三个文件拖进去，点 `Commit changes`。

### 2. 开启网站托管（GitHub Pages）
仓库 → `Settings` → `Pages` → Source 选 `Deploy from a branch` → Branch 选 `main`，文件夹选 `/ (root)` → Save。
等 1–2 分钟，页面顶部会出现网址：`https://你的用户名.github.io/仓库名/`

- 访客链接：`https://你的用户名.github.io/仓库名/`
- 管理员链接：`https://你的用户名.github.io/仓库名/admin.html`（不要分享）

### 3. 创建只能改这个仓库的令牌（Token）
1. GitHub 右上角头像 → `Settings` → 左下 `Developer settings` → `Personal access tokens` → `Fine-grained tokens` → `Generate new token`
2. Expiration（有效期）选最长；
3. Repository access 选 `Only select repositories` → 选你的仓库；
4. Permissions → Repository permissions → **Contents** 设为 `Read and write`；
5. 生成后复制令牌（只显示一次，先存好）。

### 4. 第一次进入后台
打开 `admin.html` → 填「用户名/仓库名」+ 令牌 + 自己设一个管理员密码。
之后在这台设备上只需输入密码即可。

## 日常使用
- 添加行程：填标题、日期、时间、地点、详情 → 添加
- 添加轮播：上传图片 / 小视频，或粘贴 YouTube、B站链接 → 添加；可调整顺序、删除
- 每次操作后访客页约 **1 分钟内**自动更新（GitHub Pages 重新发布需要时间）

## 注意事项
1. **安全性**：真正的“锁”是令牌。别人打开 admin.html 只能看到登录页；没有你的令牌，谁都无法修改内容。令牌用你的密码加密后存在你自己浏览器里，不会上传到任何地方。不要把令牌发给别人。
2. **换设备/换浏览器**：需要重新填一次仓库和令牌（并设一个新密码）。令牌丢了可在 GitHub 重新生成。
3. **令牌过期**：到期后后台会提示失败，重新生成一个，在登录页点「忘记密码 / 重新设置」即可。
4. **视频**：直接上传的视频建议 40MB 以内，且仓库总容量建议别超过 1GB。大的 MV/预告片请用 YouTube 或 B站链接（后台支持），不占空间。
5. **公开性**：仓库是公开的，`data.json` 里的内容别人理论上都能看到，所以不要写不想公开的信息。
6. 想用自己的域名，可在 Pages 设置里绑定（域名本身需要购买，非必需）。
