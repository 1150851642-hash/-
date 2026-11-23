# FIELDNOTE 活动平台

## 功能
- 公开活动列表、活动详情、活动封面图
- 地图导航链接、微信报名二维码 / 外部报名链接
- 报名意向表单
- 管理后台：活动增删改、图片上传、报名记录管理
- 规则与 FAQ 编辑
- SQLite 持久化数据

## 本地启动
要求 Node.js 20+：
```bash
cp .env.example .env
# 编辑 .env：设置 SESSION_SECRET 和 ADMIN_PASSWORD
npm install
npm start
```
访问 http://localhost:3000，后台 http://localhost:3000/admin。

## Render 部署（推荐）
1. 解压项目，把全部文件上传到 GitHub 仓库。
2. 注册 Render，选择 New + -> Blueprint，连接该 GitHub 仓库。
3. Render 读取 render.yaml 后创建服务。
4. 按提示填写 ADMIN_PASSWORD（设置强密码）和 SITE_URL（填写 Render 分配的网址）。
5. 部署完成后，使用 Render 提供的 onrender.com 地址访问，后台地址为该网址加 /admin。
6. 登录后台发布真实活动、上传活动图、设置地图与微信二维码。

配置了 /app/data 持久化磁盘保存数据库、会话和上传图片。换平台部署时必须确认支持持久化磁盘。Render 套餐、磁盘和免费额度政策可能调整，请以其当前控制台显示为准。

## 上线前
- 更换管理员密码与 SESSION_SECRET。
- 使用 HTTPS；Render 默认提供 HTTPS。
- 当前报名表只收集称呼、可选联系方式和备注，不收集身份证号、支付信息或微信密码。
- 上传限制 5MB，支持 JPG/PNG/WebP/GIF。
- 活动、器材、年龄、运输、场地和安全要求必须符合当地法律法规及场地方要求。
