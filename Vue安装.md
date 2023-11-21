 本地软件安装及Vue 配置

## 安装 node.js

其实我们需要的并不是`node.js`而是`node.js`里的`npm`，安装了`node.js`就等同于安装了`npm`。

### 下载安装`node.js`

安装 node.js 非常简单，首先去[node.js 官网](https://nodejs.org/en/)下载安装包。

在首页有两个可选项如下图所示：

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-5-Vue/1/img/nodejs%E6%88%AA%E5%9B%BE.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

上图中有两个版本：

- **12.14.1 LTS：**稳定版，版本较低
- **13.7.0 Current：**最新版

建议选择稳定版的下载。

下载以后，一路“下一步”即可安装成功。

### 检测 node.js 是否安装成功

node.js 安装以后，我们还要检测它是否安装成功，此时就要用到命令提示符窗口，在 Windows 系统中叫**CMD**，在 Mac 中叫**终端**。

命令提示符窗口的打开方式：

- **Mac：**点击名字叫“终端”的软件即可，苹果电脑自带的
- **Windows：**以 win10 为例，可以看一下这个[教程](https://jingyan.baidu.com/article/af9f5a2d4dae9643140a4586.html)

在命令提示符窗口中输入如下命令：

```js
node -v
```

如果看到如下图所示的版本号（版本号视你安装的版本而定，我的版本是 10.15.1），证明安装成功。

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-5-Vue/1/img/node%E6%A3%80%E6%B5%8B.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

有了 node.js 的同时也会拥有 npm（包管理工具），我们可以顺带手检测一下 npm，输入如下命令：

```js
npm -v
```

如下图所示：

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-5-Vue/1/img/npm%E6%A3%80%E6%B5%8B.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

## 安装 Vue CLI(脚手架)

Vue CLI 简单来说就是 Vue 工程的升级版，更牛逼一点，举个例子，文章开头的视频中有一些演示代码，其实那就是 Vue，只不过不适合去做大型项目，代码如下：

```html
<div id="app"></div>
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>
  new Vue({
    el: '#app',
    data: {},
  });
</script>
```

这种形式可以去写项目吗？可以，但是烦。所以需要去安装 Vue CLI。

安装脚手架的方法很简单，执行下面的命令即可：

- windows 系统：

  ```js
  npm install -g @vue/cli
  ```

- mac 系统：

  ```js
  // 如果是mac电脑，需要在命令前面加sudo
  sudo npm install -g @vue/cli
  ```

> windows 下执行命令不需要在开头输入 sudo ，大家以后执行命令自己注意一下

注意：如果执行上面的代码，很久都安装不好，因为 npm 下载的插件等都是从国外的服务器中下载，速度会很慢

可以将镜像切换成淘宝镜像，这样就可以从国内的服务器下载插件等。

### 安装 CNPM

cnpm 就可以使用淘宝镜像，国内下载速度很快

- windows 系统：

  ```js
  npm install -g cnpm --registry=https://registry.npm.taobao.org
  ```

- mac 系统：

  ```js
  sudo npm install -g cnpm --registry=https://registry.npm.taobao.org
  ```

切换镜像以后，再执行安装命令，会发现安装的速度直线上升：

```js
// 注意这里要用的是cnpm
cnpm install -g @vue/cli
```

安装完成后要验证一下脚手架是否安装成功，可以执行下面的命令：

```js
vue --version
```

当你看到显示 vue 的版本的时候，说明已经安装成功，如下图所示：

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-5-Vue/1/img/vue%E6%A3%80%E6%B5%8B.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

### 创建 Vue 工程

执行完上述所有操作以后，我们就会获得一个以 vue 开头的命令，现在我们可以用这个命令来创建 Vue 工程。

执行如下命令创建一个 Vue 工程：

```js
// vue 创建 工程名
vue create vue_first
```

此时会出现几个选项，这里选择最后一个---自定义配置（键盘上下键选择，回车确认），如下图所示：

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-5-Vue/1/img/%E5%88%9B%E5%BB%BAvue1.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

选中以后，进入自定义配置选项，勾选 Babel、Router 即可（空格选中/反选，回车确认）：

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-5-Vue/1/img/%E5%88%9B%E5%BB%BAvue2.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

下一步是询问你是否使用历史模式的路由器，可以根据自己需要来选择 N 或者 Y，然后回车确定：

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-5-Vue/1/img/%E5%88%9B%E5%BB%BAvue3.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

下一步是询问你要将 Babel 等配置文件放在哪里，我们选择放在 package.json 文件里：

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-5-Vue/1/img/%E5%88%9B%E5%BB%BAvue4.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

最后一步是询问你是否要保存这次配置，以后如果遇到相同配置的项目会比较方便，你可以根据自己需求来选择：

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-5-Vue/1/img/%E5%88%9B%E5%BB%BAvue5.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

然后会经过一系列的编译，最后创建成功一个原始的 Vue 项目，如下图所示，脚手架还给我们附赠了几个命令，

- `cd vue_first` ：进入到工程根目录，
- `cnpm install` : 编译工程，完成后会发现在项目代码中多了个 node_modules 目录
- `cnpm run serve` ：启动 vue 工程

> 如果没有按照前面的步骤安装 cnpm ，那么就用 `npm install` 、`npm run serve`

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-5-Vue/1/img/%E5%88%9B%E5%BB%BAvue6.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

> 因为我还安装了 yarn，所以图中会提示我用 yarn，如果仅仅是安装了 npm，那么会提示你们用 `cnpm run serve`
>
> > 不用纠结 yarn 主要是看项目是否成功创建

### 启动项目

下面我们就来执行这几个命令，如下图所示：

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-5-Vue/1/img/%E5%88%9B%E5%BB%BAvue7.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

此时我们已经成功的创建了一个 Vue 工程，并启动了这个工程，接下来我们可以去 **浏览器** 中打开项目的页面，脚手架给了我们两个地址：

- `http://localhost:8081/`

  > localhost 表示你自己的电脑

- `http://192.168.0.102:8081/`

  > `192.168.0.102` 是你电脑的 IP 地址，但每个人的电脑的 IP 地址不一定相同，所以你看到的可能跟截图不一样，不要纠结

我们打开其中任意一个即可。

不同的操作系统，操作可能不太一样：

- Windows 电脑 Ctrl+鼠标左键 点击地址
- Mac 电脑 command+鼠标左键 点击地址

打开以后，我们会看到一个 Vue CLI 为我们写的一个初始页面，如下图所示：

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-5-Vue/1/img/%E5%88%9B%E5%BB%BAvue8.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

到此为止，我们就完成了 Vue 的起步的所有配置，欢迎来到 Vue 世界，在接下来的章节中我们共同去感知、探索 Vue 世界～～

