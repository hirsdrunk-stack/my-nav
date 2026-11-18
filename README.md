# my-nav

这是一个静态个人导航页，浏览器标题是「我的导航」。所有链接都写在 `index.html` 里。不需要后端，不需要安装依赖，也不需要构建。

把改动提交到 GitHub 之后，Vercel 会直接把这个仓库里的网页发布出去。平时用 GitHub 网页编辑即可，不必一直开着自己的电脑。

## 用 GitHub 网页添加一个网站

1. 打开本仓库里的 `index.html`。
2. 点右上角铅笔图标（Edit this file）。
3. 找到注释「在这里添加网站」。
4. 复制下面这一整段，贴到 `<ul id="site-list">` 里面。想排在前面，就贴到上面。
5. 只改名称、网址、简介，以及分类。
6. 点 **Commit changes** 保存。

```html
<li class="site" data-cat="daily">
  <a class="card" href="https://example.com/" target="_blank" rel="noopener noreferrer">
    <p class="kicker">常用网站</p>
    <h3>示例名称</h3>
    <p class="desc">一句话说明这个网站是做什么的。</p>
    <p class="host"><span class="host-text"></span><span class="go" aria-hidden="true">↗</span></p>
  </a>
</li>
```

要改的四处：

| 改哪里 | 填什么 |
| --- | --- |
| `data-cat` | 分类代码，只能是下面四个之一 |
| `<p class="kicker">` | 和分类代码对应的中文名 |
| `href` | 完整网址，以 `https://` 开头 |
| `<h3>` 和 `<p class="desc">` | 名称和一句话简介 |

分类代码和中文名要成对，不要只改一边：

| `data-cat` | 分类名 |
| --- | --- |
| `ai` | AI工具 |
| `dev` | 开发工具 |
| `learn` | 学习 |
| `daily` | 常用网站 |

页面打开后，会按 `data-cat` 再写一次分类名，搜索和筛选也认这个代码。简介里如果要写 `&`，请写成 `&amp;`。不要往名称或简介里贴别的 HTML 标签。

## 修改或删除

还是用网页编辑 `index.html`。改名称、网址或简介即可。删除时，从 `<li class="site"` 删到对应的 `</li>`，不要留下半截标签。

页面上的顺序就是文件里的顺序。

## 不用改的部分

搜索、分类筛选和浅色 / 深色切换写在 `index.html` 底部的脚本里，一般不用动。样式也在同一个文件里。

浏览器标题在 `<title>`，页面上的大标题在 `<h1>`。两处现在都是「我的导航」。

## 本地电脑（可选）

不要求在自己的电脑上开发。如果手头已经有编辑器，改完 `index.html` 再提交也可以。没有构建命令，用浏览器直接打开这个文件就能看。

## 发布

`vercel.json` 把项目设成静态站点：框架为 Other，跳过安装和构建，发布仓库根目录。首页是根目录的 `index.html`。

不要把密码、密钥、个人账号或统计代码写进仓库。
