# 🎄 圣诞树默契猜一猜

## 文件说明
| 文件 | 用途 |
|------|------|
| `index.html` | 答题页，所有朋友打开这个 |
| `admin.html` | 管理页，**只有你（主人）** 打开，设置题目和自己的答案 |
| `supabase/schema.sql` | 数据库建表脚本，在 Supabase 控制台执行一次 |

---

## 使用流程

### 第1步：建 Supabase 数据库（一次性）
1. 打开 https://supabase.com 注册，创建一个免费 Project
2. 左侧 **SQL Editor** → 把 `supabase/schema.sql` 内容粘贴进去 → Run
3. 左侧 **Settings → API**，复制两个值：
   - Project URL
   - anon public key

### 第2步：设置你的答案（每次出题前）
1. 手机/电脑浏览器打开 `admin.html`
2. 填入 Supabase URL 和 Key（只需填一次，之后自动记住）
3. 输入你的昵称
4. 编辑题目（可增删、改文字、改选项），为你自己的每题选 A 或 B
5. 点「💾 保存到圣诞树」

### 第3步：分享给朋友
1. 把 `index.html` 的部署链接（Cloudflare Pages 或任意静态托管）发给朋友
2. 朋友打开后自动看到你的题目和昵称，凭了解程度猜答案
3. 提交后默契分决定挂件挂在圣诞树第几层（猜对越多越高）
4. 圣诞树实时同步更新

---

## 部署到 Cloudflare Pages
1. 把文件夹放到 GitHub
2. https://pages.cloudflare.com → 连接仓库 → Build command 留空 → Deploy
3. 部署后把生成的 URL 填到 `admin.html` 的 Supabase 配置区
4. 把 URL 发给朋友即可

## 本地预览
```bash
cd 圣诞树默契
python -m http.server 8080
# 浏览器打开 http://localhost:8080（答题页）
# 浏览器打开 http://localhost:8080/admin.html（管理页）
```
本地预览时数据库操作不工作（跨域），需要部署后测试完整功能。
