## 第一步： 
创建项目文件夹docute-demo
## 第二步： 
创建index.html并向其中输入以下内容：
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <title>My Docs</title>
    <link rel="stylesheet" href="https://unpkg.com/docute@4/dist/docute.css">
  </head>
  <body>
    <div id="docute"></div>
    <script src="https://unpkg.com/docute@4/dist/docute.js"></script>
    <script>
      new Docute({  title: 'Docute Demo',
          // 代码高亮配置  highlight: [    'typescript', 'go', 'python'],
          // 主题切换开关  darkThemeToggler: true,
          // 顶部banner配置  banner: `Please <a href="https://donate.com/link">   donate</a> <ExternalLinkIcon /> to support this project!`,
          // 顶部导航栏配置  nav: [// A dropdown menu{  title: '语言',  children: [{  title: '2',  link: '/'},{  title: '1',  link: '/'}]},{  title: 'Home',  link: '/'},{  title: 'MyBlog',  link: 'https://www.u1s1.vip'}],
          // 侧边栏配置   sidebar: [// A sidebar item, with child links{  title: '教程',  children: [{  title: '快速开始',  link: '/a/start'},{  title: '安装',  link: '/install'}]},// An external link{  title: 'GitHub',  link: 'https://github.com/egoist/docute'}]})
    </script>
  </body>
</html> 
```
如上，Docute的主页就是index.html，项目的配置都在script标签中进行。

## 第三步： 
创建首页README.md文件并向其中输入以下内容：

```
## 首页
​
欢迎来到Docute的世界。
​
> 这是引用
​
---
​
1. 有序1
2. 有序2 
```

1.启动预览

>在完成以上步骤后，我们就可以使用Python的http.server或者Caddy或者Nginx等服务器将Docute项目托管，然后在浏览器进行预览。

我是在vscode安装liveserver插件运行的,查看效果

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f4580b7e21ee4cc18c0755c2d032580b~tplv-k3u1fbpfcp-zoom-in-crop-mark:4536:0:0:0.image)

2.顶部导航栏配置

>在Docute中，顶部导航栏配置是nav配置块。我们可以在nav中添加顶部菜单，下拉菜单等。

```
nav: [
    // 下拉菜单
  {
        title: '语言',
        children: [
          {
                title: '2',
                link: '/'
          },
          {
                title: '1',
                link: '/'
          }
      ]
  },
    // 独立菜单
  {
        title: 'Home',
        link: '/'
  },
  {
        title: 'MyBlog',
        link: 'https://www.u1s1.vip'
  }
], 

```
3.侧边栏配置

>在Docute中，顶部导航栏配置是sidebar配置块。我们可以在sidebar中添加侧边导航目录，独立菜单，下拉菜单等。

```
sidebar: [
    // 侧边导航
  {
        title: '教程',
        children: [
          {
                title: '快速开始',  // 标题
                link: '/a/start'   // 标题对应的markdown文件
          },
          {
                title: '安装',
                link: '/install'
          }
      ]
  },
    // 外部链接
  {
        title: 'GitHub',
        link: 'https://github.com/egoist/docute'
  }
] 

```


4.其他配置

> 我们还可以在index.html的script中对Docute的代码高亮、主题切换等进行配置。

```
// 站点标题
title: 'Docute Demo',
// 代码高亮
highlight: [
'typescript', 
'go', 
'python'
],
// 主题切换开关
darkThemeToggler: true,
// 顶部banner，主要用于广告和提示
banner: `Please <a href="https://donate.com/link">
donate</a> <ExternalLinkIcon /> to support this project!`, 
</div>
```

5.更多的配置

```
// 站点logo
logo: '',
// 站点在线编辑的github项目路径
editLinkBase: 'https://github.com/USER/REPO/blob/master/docs',
// 编辑文档的提示语
editLinkText: '编辑我',
// Docute主题根据系统主题来，windows10+，macOS (Mojave)+
detectSystemDarkTheme: true,
// 站点布局风格，全屏、居中、居左可选
layout: 'narrow ',
// 站点底部信息
footer: 'xxx',
// 开启图片缩放
imageZoom: true 

```
6.创建示例文档

>前面我们已经在sidebar中配置了快速开始和安装两个导航菜单。其中快速开始的路由是/a/start即在index.html所在路径下需要创建a/start.md文件；安装的路由是install，即需要在index.html的路径下创建名为install.md的文件。

index.html所在路径为项目根路径。
我们创建a/start.md文件并输入以下内容：

```
## start
> 我的生活

```
完成后开始调整你自己的项目之旅吧！！！！





