# Zero Group 网站：上线设置说明

目标：网站代码放在 **GitHub 私有仓库**，由 **Cloudflare Pages** 自动构建；再用 **Cloudflare Access** 限制只有指定的人能看。每次在 GitHub 上提交修改，网站几分钟后自动更新。

预计用时：第一次设置大约 30–45 分钟。

---

## 第 1 步：建 GitHub 私有仓库并上传文件

1. 登录 GitHub，点右上角 **+** → **New repository**。
2. Repository name 填 `zero-group-site`，选择 **Private**，其他选项都不勾，点 **Create repository**。
3. 在新仓库页面点 **uploading an existing file**。
4. 把解压后的 `zero-group-site` 文件夹**里面的所有文件和文件夹**拖进去（不要拖最外层的文件夹本身）。
   - Mac 上以 `.` 开头的隐藏文件夹（`.github`、`.devcontainer`）默认看不到，在 Finder 里按 `Cmd + Shift + .` 可以显示出来。它们不上传也不影响网站。
5. 页面底部点 **Commit changes**。

> 网页拖拽一次最多上传 100 个文件。如果提示太多，可以分两次上传：先传 `_pages`、`_data`、`_news`、`_bibliography`、`assets`，再传剩下的文件。

## 第 2 步：用 Cloudflare Pages 自动构建

1. 注册或登录 [Cloudflare](https://dash.cloudflare.com/)，免费账号就够。
2. 左侧菜单进入 **Workers & Pages** → **Create** → 选 **Pages** → **Connect to Git**（导入已有的 Git 仓库）。
3. 授权 Cloudflare 访问 GitHub 时，选 **Only select repositories**，只勾选 `zero-group-site`。
4. 选择仓库后，构建设置填写：

   | 设置项 | 填写 |
   |---|---|
   | Project name | `zero-group`（网址会是 `zero-group.pages.dev`；如果被占用，换个名字） |
   | Production branch | `main` |
   | Framework preset | `Jekyll` |
   | Build command | `bundle exec jekyll build` |
   | Build output directory | `_site` |

5. 展开 **Environment variables**，添加一项：`JEKYLL_ENV` = `production`。
6. 点 **Save and Deploy**。第一次构建要安装依赖，大约需要 5–10 分钟。
7. 构建完成后会显示网址，例如 `https://zero-group.pages.dev`。

**如果项目名不是 `zero-group`**：打开仓库里的 `_config.yml`，把 `url: https://zero-group.pages.dev` 改成你实际的网址，然后提交。

**如果构建失败**：点开那次部署查看日志（Build log），把最后几十行发给我，我帮你看。

## 第 3 步：用 Cloudflare Access 限制访问

Cloudflare 自带的开关默认只保护"预览版本"，主网址 `*.pages.dev` 需要按下面的步骤额外设置（参考 [Cloudflare 官方说明](https://developers.cloudflare.com/pages/platform/known-issues/)）：

1. **Workers & Pages** → 你的项目 → **Settings** → **General**，点 **Enable access policy**。
   - 第一次使用时会让你开通 Zero Trust，选择 **Free** 方案（50 人以内免费）。可能要求填写付款方式，但免费方案不会扣费。
2. 在刚生成的 Access policy 旁边点 **Manage**。
3. 进入 **Access** → **Applications**，选择你的项目，点 **Configure**。
4. 在 **Public hostname** 里，把 Subdomain 字段中的 `*` 删掉后保存（如果报错，先给这个应用改个名字）。现在它保护的就是主网址 `zero-group.pages.dev`。
5. 回到项目的 **Settings** → **General**，再点一次 **Enable access policy**（这次生成的规则保护预览版本）。
6. 确认 **Access** → **Applications** 里有两条：一条是 `zero-group.pages.dev`，一条是预览版本。
7. 设置谁能看：打开这两条应用的 **Policies**，规则设为 **Include → Emails**，填入允许访问的邮箱（如 Giuseppe 和组员的邮箱）；或者用 **Emails ending in** 填 `@kth.se`，允许所有 KTH 邮箱访问。

设置好以后，别人打开网址时会先看到登录页，输入邮箱 → 收验证码 → 才能进入网站。

## 第 4 步：日常修改

在 GitHub 上打开任意文件 → 点**铅笔图标** → 修改 → **Commit changes**。Cloudflare 会自动重新构建，几分钟后刷新网站就能看到。

具体改哪个文件，看仓库里的 `README.md`。

## 以后正式公开

有两种方式：

- **继续用 Cloudflare**：在 **Access** → **Applications** 里删掉那两条规则，网站立刻对所有人开放，网址不变。
- **换到 GitHub Pages**：
  1. 把仓库改成 Public（Settings → General → Danger Zone → Change visibility）。**注意：以前所有的提交历史都会公开。**
  2. 把 `.github/deploy.yml.later` 移动到 `.github/workflows/deploy.yml`。
  3. Settings → Pages → Source 选 **Deploy from a branch**，分支选 `gh-pages`。
  4. 把 `_config.yml` 里的 `url` 改成新网址。

无论用哪种方式，如果想要固定的网址（比如 KTH 子域名或自购域名），都可以在 Cloudflare 的项目里 **Custom domains** 绑定，或在 GitHub Pages 设置里绑定。绑定自定义域名时，记得也为它加一条 Access 规则，否则登录页会出现但无法使用。
