# 网站维护说明

这是一个纯静态网站，可直接部署到 GitHub Pages。访客可以浏览、下载简历和通过邮件留言，但不能在线修改网站。只有拥有 GitHub 仓库写入权限的账号才能发布更新。

## 文件结构

- index.html 网站页面、三语文本与交互功能
- site-config.js 作品链接、邮箱、电话和 GitHub 编辑入口
- assets/cv/Kaitong-Zhang-CV-ZH.pdf 中文简历
- assets/cv/Kaitong-Zhang-CV-EN.pdf 英文简历
- assets/cv/Kaitong-Zhang-CV-PT-BR.pdf 巴西葡语简历

## 更新作品链接

1. 打开 site-config.js。
2. 找到对应作品卡片。
3. 把空白 url 改为完整的公开 HTTPS 链接。
4. 提交修改并等待 GitHub Pages 自动更新。

链接可以指向 Notion、Google Drive、OneDrive、Behance、YouTube、Vimeo、Bilibili、小红书、GitHub、公开 PDF 或独立案例页面。

## 可选社媒链接

是否展示社媒由你决定。打开 site-config.js，在 owner.socialLinks 数组中添加公开账号，例如：

`{ name: "LinkedIn", url: "https://www.linkedin.com/in/your-name/" }`

只支持 HTTPS 地址；数组为空时页面不会显示社媒区域。不要添加私人账号或你不希望求职访客看到的内容。

## 更新简历

导出新的 PDF 后，保持文件名不变并覆盖 assets/cv 中的对应文件：

- 中文：Kaitong-Zhang-CV-ZH.pdf
- 英文：Kaitong-Zhang-CV-EN.pdf
- 巴西葡语：Kaitong-Zhang-CV-PT-BR.pdf

保持文件名不变后，不需要修改 index.html。

## 设置本人维护按钮

创建 GitHub 仓库后，在 site-config.js 的 owner 部分填写 repositoryUrl、configEditUrl 和 cvFolderEditUrl。随后用网站网址加上 ?owner=1 打开站长维护区；正常访客看不到该区。

GitHub 会要求登录，并只允许具有仓库写入权限的账号提交更改。不要把密码、访问令牌或私人密钥写入网站文件。

## 访客留言

留言表单使用 mailto 打开访客自己的邮件客户端。网站不会保存留言，也不需要数据库或第三方表单服务。

如果以后希望访客无需邮件客户端即可提交并保存留言，可接入 Formspree、Netlify Forms 或自建后端，并增加验证码、频率限制和隐私说明。

## GitHub Pages 部署

1. 新建 GitHub 仓库。
2. 将本文件夹中的全部内容上传到仓库根目录。
3. 打开仓库 Settings 和 Pages。
4. 选择从默认分支根目录部署。
5. 等待 GitHub 提供网站地址。

index.html 必须位于仓库根目录，assets/cv 目录结构不可随意更改。
