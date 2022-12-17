# Hexo+stun主题+Gitee5分钟快速搭建你的个人Blog

## 环境配置

>首先要下载[Node.js](https://links.jianshu.com/go?to=http%3A%2F%2Fnodejs.cn%2F)，然后安装[Git](https://links.jianshu.com/go?to=https%3A%2F%2Fgit-scm.com%2Fdownloads)，接着注册[码云](https://links.jianshu.com/go?to=https%3A%2F%2Fgitee.com%2F)，最后安装Hexo，Hexo安装命令行(cmd 或 gitbash):
```
npm install hexo-cli -g
```
速度慢可以先改一下安装源:

```
npm config set registry https://registry.npm.taobao.org
```
## Hexo搭建
>目录说明和基础文件配置可以查看文档->https://hexo.io/zh-cn/
- 在想要存放博客的目录里右键打开gitbash，然后输入：
```
hexo init
```
- 接着生成静态页面：

```
hexo g
```
- 然后启动本地服务，查看界面是否生成：

```
hexo s
```
>将`http://localhost:4000`复制到浏览器查看，默认主题为`landscape`。(在下面的每次配置中，对根目录的`_config.yml`修改后都要重新执行`hexo g`，同时可以不断刷新本地服务查看效果)

 ## 主题
 
 >其他具体相关配置和文件目录说明可参考文档->https://theme-stun.github.io/docs/zh-CN/guide/quick-start.html

博客系统至此基本搭建完，我们接下来更换主题stun。在`themes`文件夹下右键gitbash，输入下面的命令:

```
git clone https://github.com/liuyib/hexo-theme-stun.git
```
打开根目录下的`_config.yml`配置文件，在theme修改主题：
![1671270584683.jpg](https://img-blog.csdnimg.cn/img_convert/46f021e72ec282b86110a981e1356f74.png)

### 写文章

- 新建文章方法：在项目根目录，打开gitbash：

```
hexo new page about
```

然后就可以在`/source/_posts`找到markdown文件。

我的目录如下：

![image.png](https://img-blog.csdnimg.cn/img_convert/dbeb8b9b7c970de32c88fa8c4c01dbe4.png)

- 使用已有markdown文件：复制到上述目录即可，注意在文件头加上一些信息，基本结构：

![image.png](https://img-blog.csdnimg.cn/img_convert/ddc87a2e721cedcc0edeb7e908de8d59.png)

具体配置可参考上面提供的文档链接

## 部署到码云

>首先在码云上创建一个仓库，建议是仓库名用用户名，这样的话生成的gitee pages的域名很短。复制仓库连接。
>
在项目根目录下的`_config.yml`中，修改deploy的值，repo设置为仓库链接：

![image.png](https://img-blog.csdnimg.cn/img_convert/6a5134b269cf1c89dc6aedb118ca8554.png)

然后修改git用户名和邮箱为码云的用户名和邮箱：

```
git config --global user.name 码云的名字
git config --global user.email 码云的邮箱
```
接着安装`hexo-deployer-git`:

```
npm install hexo-deployer-git --save
```

然后部署到仓库：依次执行3个命令

```
hexo g
hexo d
```
接着配置gitee pages：

![image.png](https://img-blog.csdnimg.cn/img_convert/23804725e30c8e889ce961bebbf6be65.png)

接着在项目根目录的`_config.yml`中修改url和root:  
root设置为仓库名(我这里没有子目录，就设置为空就行)。

![image.png](https://img-blog.csdnimg.cn/img_convert/7aea723839b7c5240e610ae51033a772.png)

最后重新部署一遍博客即可：

```
hexo clean
hexo g
hexo d
```
通过gitee pages的域名访问自己的博客了

## 踩坑出现的问题（重点）

### 布局是乱的且没有样式
>通过键盘SHIFT+F5刷新浏览器缓存即可出现

### 图片没有显示出来

如果图片显示有问题，可以使用下面这种方法：

先将根目录的`_config.yml`中的`post_asset_folder`设置为`true`:

![image.png](https://img-blog.csdnimg.cn/img_convert/6004a69b21390ba6cca74f08f547a405.png)


这样的话，新建文章时还会建立一个同名的文件夹，我们可以图片放在这个文件夹下。

然后下载一个插件，根目录下：

```
npm install https://github.com/CodeFalling/hexo-asset-image --save
```

### 图片还是没有出来且点击头部导航跳转404

看你自己创建的仓库图中指示的箭头是否都跟你自己的个人用户名称一样

*我卡在这里被折磨了一天最后解决*

![image.png](https://img-blog.csdnimg.cn/img_convert/0d2edf60d23dec66618bce19bbee8512.png)



## 我的博客

- 可参考我的博客进行配置

https://lin-xiuer.gitee.io/

- 具体代码放在GitHub

https://github.com/linweiqian/GitteeBlog.git


