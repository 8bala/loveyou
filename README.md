# 表白信封使用教程

## 本地调试

### 安装 Git
教程：<a href="https://www.bilibili.com/video/BV1BE411g7SV" target="_blank">bilibili.com/video/BV1BE411g7SV</a>

下载：<a href="https://git-scm.com/downloads" target="_blank">git-scm.com/downloads</a>

### 安装 XAMPP
教程：<a href="https://www.bilibili.com/video/BV1e7411u7qY" target="_blank">bilibili.com/video/BV1e7411u7qY</a>

下载：<a href="https://www.apachefriends.org/download.html" target="_blank">apachefriends.org/download.html</a>

### 本地部署
首先注册一个 GitHub 账号并 fork 一份本仓库到你自己的账号
<br>
在 cmd 中切换到 XAMPP 的 htdocs 目录下，克隆仓库：
```
git clone https://github.com/你的github用户名/eLuvLetter.git
```

进入 ./eLuvLetter/font/ 目录下打开 content.json，按如下说明自定义配置：

```
{
    "to"        : "信封收件人",
    "from"      : "信纸落款",
    "recipient" : "信纸收件人",
    "bgm"       : "BGM URL",
    "text"      : "信纸内容"
}
```

其中demo里符号 `^n` 的含义是打字机停顿 n 毫秒，

BGM URL可以是 demo 代码中带的默认 mp3 目录，也可以是网络 mp3 直链(注：最好不用 API 获取 mp3，可能会被跨域封锁)
<br>
如果使用默认目录，可将自己的 mp3 重命名成 bgm.mp3 覆盖掉 ./eLuvLetter/bgm 下的 bgm.mp3 实现自定义修改 BGM

### 本地展示
在 XAMPP 上打开 Apache，进入 <a href="http://localhost/acg-album" target="_blank">localhost/acg-album</a>
<br>
建议使用本地展示调试完毕后再进行下一步

## 部署到 Vercel 及广域网展示
首先将修改过的本地代码同步到你的 GitHub 账号上：

命令行进入 ./eLuvLetter 后
```
git add .
git commit -a
输入 :wq! 回车
git push
```

再进入<a href="https://vercel.com/login" target="_blank">vercel 官网</a>

使用你自己的 GitHub 账号授权登录，点击 `+ New Project`，

在 Import Git Repository 的搜索框中键入关键字 eLuvLetter 找到之前 fork 的那个仓库，

点击 `Import`，修改 Configure Project 下的 PROJECT NAME 

保证 PROJECT NAME 不与别人冲突后点击 `Deploy`

部署完成后，可在广域网中访问 `https://%PROJECT NAME%.vercel.app` 查看网页。(其中 %PROJECT NAME% 就是刚刚 Configure Project 下修改的 PROJECT NAME)

## 未来工作
目前信纸内容有字数限制，未来有余力可在信纸上添加滚轴实现字数扩展，也欢迎各位大神能在此基础上把这些问题优化掉来 merge。