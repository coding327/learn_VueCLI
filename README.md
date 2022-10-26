## Vue的脚手架Vue CLI
之前在`vue2`搭建项目中，已经提到过一点`Vue CLI`，而它本身是基于`webpack`开发的【`webpack`是基于`JavaScript`开发的】，这一篇我将更加详细的介绍`Vue CLI`

## Vue CLI脚手架
什么是`Vue`脚手架?
  - 前面已经学习了如何通过`webpack`配置`Vue`的开发环境，但是在真实开发中我们不可能每一个项目从头来完成所有的`webpack`配置，这样会让开发的效率会大大的降低;
  - 所以在真实开发中，我们通常会使用脚手架来创建一个项目，`Vue`的项目我们使用的就是`Vue`的脚手架;
  - 脚手架其实是建筑工程中的一个概念，在我们软件工程中也会将一些帮助我们搭建项目的工具称之为脚手架;

`Vue`的脚手架就是`Vue CLI`:
  - `CLI`是`Command-Line Interface`，翻译为命令行界面;
  - 我们可以通过`CLI`选择项目的配置和创建出我们的项目;
  - `Vue CLI`已经内置了`webpack`相关的配置，我们不需要从零来配置;

## Vue CLI安装和使用
**以下操作默认你电脑已经有`node`环境了，因为我们需要使用`npm`工具，没有安装`node`环境，可以去安装一下，后面我也会写一篇`node`安装的文章**

1. 安装`Vue CLI`(目前最新的版本是v5.0.8):
  - 我们是进行全局安装【在该电脑的任何位置都可以使用`vue`命令】，这样在任何时候都可以通过`vue`的命令来创建项目;
  ```bash
  # 打开你的CMD窗口，或者vscode终端输入如下命令
  npm install @vue/cli -g
  ```
2. 升级`Vue CLI`:
  - 如果是比较旧的版本，可以通过下面的命令来升级
  ```bash
  # 打开你的CMD窗口，或者vscode终端输入如下命令
  npm update @vue/cli -g
  ```
3. 通过`Vue`的命令来创建项目
  ```bash
  vue create 项目的名称
  ```

注意一个细节，我们安装的包是`@vue/cli`而使用的命令是`vue`，这两个是没有任何关系的，其实在我们安装`@vue/cli`的包里面有个`package.json`，里面有个配置选项`bin: { 'vue': 'bin/xxx.js' }`，其中配置的是`vue`所以我们使用的命令名称也就是`vue`

## 使用Vue CLI脚手架创建vue项目

这里的话，我先创建一个`learn_VueCLI`文件夹来存放咱们脚手架创建的项目，然后在**它这个目录下**打开`CMD`窗口或者`vscode`终端，输入如下命令来创建一个项目
```bash
vue create vuecli_demo
```

输入后回车，会出现一个选择界面如下图：
![10186](https://img.coding327.top/blogImg/10186.png)

- 第一个选项是它会默认帮你创建一个`vue3`项目，并且包含`babel`和`eslint`
- 第二个选项是它会默认帮你创建一个`vue2`项目，并且包含`babel`和`eslint`
- 第三个选项是手动选择特性，哪些需要哪些不需要用户自己选择

按上下方向键可以进行选择，这里我们选择第三个，回车

接着出现如下第二个界面：
![10187](https://img.coding327.top/blogImg/10187.png)

这个是让你选择特性了，当然它其中也说了，按住空格是选择【括号内就会带上星号】再按一下就会取消选择，按回车进行下一步
- 第一个让你选择`Babel`，让`ES6`代码转为`ES5`代码【这个我们需要用，选上】
- 第二个`TypeScript`【这个也可以选上】
- 第三个`Progressive Web App (PWA) Support`即`PWA`，主要是给应用程序做很多缓存之类的东西【应用比较少，一般不选上】
- 第四个`Router`是路由【开发项目基本要选上，这里我只是创建临时项目，我就不选上了】
- 第五个`Vuex`是状态管理【开发项目基本要选上，这里我只是创建临时项目，我就不选上了】
- 第六个`CSS Pre-processors`是`css`预处理器【如果你想要使用`less`或者`sass`、`stylus`，就选上，它会帮你配置好，开发项目基本要选上，这里我只是创建临时项目，我就不选上了】
- 第七个`Linter / Formatter`是对代码格式做检测用的【开发项目基本要选上，这里我只是创建临时项目，我就不选上了】
- 第八个`Unit Testing`是单元测试【这个根据公司，有些公司可能会让你写测试用例，那么你就选上，这里我只是创建临时项目，我就不选上了】
- 第九个`E2E Testing`是端到端测试即`end2end`【这个测试我们现在基本上也不写这个东西，不用选上】

最后将选择好后，进行回车进入下一步
出现如下第三个选择界面：
![10188](https://img.coding327.top/blogImg/10188.png)

这个是让我们选择`vue`的版本，按住上下方向键可以进行选择，这里我们选择`3.x`即`vue3`版本，然后回车
出现如下第四个选择界面：
![10189](https://img.coding327.top/blogImg/10189.png)
这个是让我们选择像`Babel`、`ESlint`和`etc`是生成单独、分离的配置文件，还是放到`package.json`文件里面，放到`package.json`的话，会让这个文件过大，不方便管理，所以我们一般选择`In dedicated config files`然后回车

出现如下第五个选择界面：
![10190](https://img.coding327.top/blogImg/10190.png)
大概意思是把刚才我们的选择是否保存为预设，下一次选择的时候就不需要刚才这么多步骤了，这个选择就看个人了
这里我们可以试一下它这个保存为预设，输入`y`，然后回车
它会让我们起一个名字【`Save preset as`】，随便起一个吧，就叫`cake`，输完后回车，然后就会帮我们创建了

这里我们来使用一下刚刚保存的那个预设，再开一个终端【注意也是在刚刚那个目录下】，重新创建第二个新项目
```bash
vue create abc
```
敲完命令回车，出现如下选择界面：
![10191](https://img.coding327.top/blogImg/10191.png)

上面多了一个选项，多的那个就是我们刚刚保存的预设，我们已经创建一个项目了，直接按住`CTRL + C`把它取消掉

## 项目的目录结构
这里我放在一张图里面了
![10192](https://img.coding327.top/blogImg/10192.png)

关于浏览器适配的这个文件，`.browserslistrc`文件里的内容一般使用默认的，这里我也解释一下：
```txt
> 1%
last 2 versions
not dead
not ie 11
```
- `> 1%`是指市场份额
- `last 2 versions`是指最新的两个版本
- `not dead`是指还在维护
- `not ie 11`是指非`ie 11`浏览器


## 项目运行
打开`package.json`文件，我们可以查看其中的脚本，之前学习过`webpack`这里看一下就能知道运行的命令了
```json
{
  ...
  "scripts": {
    "serve": "vue-cli-service serve",
    "build": "vue-cli-service build"
  },
  ...
}
```

首先在项目根目录打开终端，千万别打开错终端了，然后运行如下命令即可
```bash
npm run serve
```

浏览器运行正常，并且包含了热更新

运行一下打包
```bash
npm run build
```
打包后这个`dist`目录结构和我们之前学习`webpack`打包目录结构非常相似

## vue脚手架npm run serve
> 当我们去执行`npm run serve`它执行的是`vue-cli-service serve`

之前学习`webpack`的时候，执行的是`webpack serve`命令，它其实会去`node_modules/.bin`目录下去找`webpack`，执行的是这个`webpack`文件里面的代码，而这里是`vue-cli-service`，所以它也是去`node_modules/.bin`目录下去找`vue-cli-service`，执行它里面的代码【它里面有三个这样的文件，没有后缀名的是对应`unix`，`.cmd`后缀名的是`cmd`窗口下的执行脚本命令，`.ps`后缀名是对应`powershell`你执行的脚本命令】
这里面的代码有很多符号，比如我打开一个`vue-cli-service.cmd`文件里面有如下代码
```cmd
"%_prog%"  "%dp0%\..\@vue\cli-service\bin\vue-cli-service.js" %*
```
其实是个软链接【符号链接，操作系统帮忙做的事】，当准备执行这个文件时候，它会去找到它真实代码所在的位置，然后去执行它的真实代码，上面路径中有个`@vue`，在`node_modules`下我们可以找到这个文件夹，它里面有个`cli-service`，它执行的是这个文件，为什么说执行的是这个文件呢？把它里面`package.json`文件打开，里面有个`"bin": {"vue-cli-service": "bin/vue-cli-service.js"},`，所以这个`vue-cli-service`就是命令名称，相当于执行的是后面那个文件
可能有人会有疑问？
脚手架那个`vue`命令名称能在终端使用，而这个`vue-cli-service`却无法在终端直接使用，主要是因为`vue-cli-service`是局部安装，想要执行它，得用一些让它去`node_modules`下去找的方法，如`npx`、`package.json`里的脚本，`Vue CLI`是全局安装。


