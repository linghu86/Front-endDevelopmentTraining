# 第1讲 Web前端开发环境准备
tags: Web前端开发 传统开发转型 nodejs大前端 

[TOC]


## 1 版本管理 Git

### 安装Git 
安装文件：Git_V1.9.5_preview20150319.1435310867.exe  
下载地址：[百度中心提供的安装包](http://rj.baidu.com/soft/detail/30195.html?ald)，适用windows环境，已含32位与64位。

安装结束后，在cmd命令行输入

```bash
git --version
```

如果返回版本号，即为安装成功。  
安装成功，在右键菜单会显示 **Git Bash** 菜单，可以快速打开当前目录的命令行窗口  
如果没有上述效果，要检查系统变量**PATH**是否没有设置，如  

```
C:\Program Files\Git\bin;C:\Program Files\Git\cmd;
```

### Git可视化管理工具-SourceTree

安装文件：SourceTreeSetup_1.6.20.exe
下载地址：[sourcetree官网](https://www.sourcetreeapp.com)

SourceTree是免费软件，且有官方中文版，并同时有win和mac版本。但需要注册，注册是免费的。注册可能需要国外邮箱，如Gmail,国内邮箱可能无法注册（没有测试过)。

SourceTree使用比较简单，功能直观方便，是免费Git工具中最好的。

**安装SourceTree时要注意的事项**

- 安装前要确认 安装了git或是Mercurial， 这里选择git。
- 在SourceTree安装结束后，还要继续提示要安装Mercurial，选择“我不想使用Mercurial”即可。
- 如果还有提示要安装其它东西，直接点取消即可。
- **第一次运行SourceTree时，要先在“工具/选项”菜单中，设置全局的帐号和邮箱，即gitHub的帐号。**
- 如果每个项目的帐号都不一样，还可以在项目的最右侧的“设置”按钮单独设置。


> 如果在提交时出现下列提示
> 原因：你没有设置邮箱，你可以用提示中所说两条命令设置一下。
> 也可以在“工具/选项”菜单中，设置全局的帐号和邮箱

```bash
git -c diff.mnemonicprefix=false -c core.quotepath=false commit -q -F C:\Users\AppData\Local\Temp\xxxxx.fz2

*** Please tell me who you are.

  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"

```
 

> *如果不想使用`SourceTree`，还可以使用`Tortoisegit32`。*

### Git 初学者要了解的几个概念

对于Git初学者，建议先了解几个简单概念，平时使用SourceTree完成相关功能。在熟练使用SourceTree后，再进一步了解SourceTree的各种功能，实际对应的Git命令。再去系统学习Git命令会比较顺利。

 - 工作区
 - 暂存区
 - 本地仓库
 - 本地master分支
 - 暂存文件（add)
 - 提交
 - 远程仓库
 - 远程master分支
 - 远程Head
 - 推送
 - 拉取

### Git学习资源

 1. Git教程 [廖雪峰](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/)
 2. [Pro Git（中文版）](http://git.oschina.net/progit/) 

### Git远程仓库资源

 1. [github](https://github.com/):国外开源项目仓库，免费可以创建公开项目，私有项目需要按月收费
 2. [开源中国代码托管](http://git.oschina.net/):免费使用，可创建公开和私有项目。**推荐**

##2 NodeJs

### 安装NodeJs

安装文件：

 - node-v0.12.2-x64.msi [win64]
 - node-v0.12.7-x86.msi [win32]
 
建议从官网下载安装，其它第三方打包的安装路径比较乱。

官网地址：[NodeJs](https://nodejs.org/en/)

安装结束后，在cmd命令行窗口键入

```
node -v
npm -v
```

两条命令均可以返加版本号，表示安装正确。  
如果没有返回版本号，检查PATH环境变量是否没有设置，如
`C:\Program Files\nodejs\`

### 安装淘宝镜像命令`cnpm` 

```
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

> *注意：*在网上一般文章会在命令前加$，表示处于命令行Shell窗口环境，  
> 在windows系统下，用右键菜单 `Git Bash` 进入的命令行窗口提示符即为`$`
> 但本文为了统一，命令前不加 $ 

[淘宝镜像地址](http://npm.taobao.org/)

**安装`cnpm`后，凡是 `npm` 命令均可改用 `cnpm` 命令代替**，即改为访问淘宝镜像。

### 需要全局安装的常用模块

如果没有特别设置，全局安装的模块一般在  
`C:\Users\<用户名>\AppData\Roaming\npm\node_modules` 目录下。

#### 全局安装的意义

全局安装的模块，可以在命令行窗口直接调用，并作用于当前命令行窗口所指向的目录。一般来说大部分模块都不需要在命令行直接调用。

#### 常用全局模块

**bower**:包管理工具  **推荐指数：** `*****`
```
cnpm install -g bower
```

**grunt**:工程自动化管理工具，现在gulp逐渐取代grunt,但前端初学者仍需要了解如何使用grunt
```
cnpm install -g grunt-cli
```
> *注意：*全局安装是 `grunt-cli`，不是`grunt`, `grunt-cli`是`grunt`的命令行工具

**gulp**:新的工程自动化管理工具，效率比grunt高，编写任务脚本比grunt简明
```
cnpm install -g gulp
```
> *注意：*全局安装的只是命令行工具，具体工程项目仍需要在当前目录安装gulp

**jshint**:<span id="jshint">代码规范检查工具 </span>

```
cnpm install -g jshint 
```

### 对Nojs初学者建议

 - 需要先有一定的Javascript基础
 - 直接先学习ExpressJs,因为对初学者而言，需要用到的NodeJs的知识，Express已全部封装好了
 - [Express 4.x 中文网](http://www.expressjs.com.cn)
 - 掌握了ExpressJs之后，再去看NodeJs的文档，对ExpressJs已经封装过的部分就可以跳过了，这样可以减少时间的浪费。

----------

## 3 MongoDB

[MongoDB 2.6 中文文档](http://docs.mongoing.com/manual-zh/index.html)

### 为什么要使用MongoDB
MongoDB是目前最流行的NoSQL数据库，前端开发者都需要了解至少一种NoSQL数据库。不过需要注意的是，不是什么数据都适合使用MongoDB来存储。在选择使用MongoDB时，要区分清楚哪些数据适合使用MongoDB存储，哪些不适合。 

### 安装MongoDB
> *注意：*  
> 
 - MongoDB新的版本不支持 winXP  
 - MongoDB在正常生产环境使用时，建议是64位环境下使用。  
 - 因为32位数据库最大只能为2G  

安装前先阅读：[在Windows系统下安装MongoDB](http://docs.mongoing.com/manual-zh/tutorial/install-mongodb-on-windows.html)

安装文件： 

- `win32` mongodb-win32-i386-3.0.6-signed.msi  
- `win64` mongodb-win32-x86_64-2008plus-ssl-3.0.6-signed.msi

### 检查PATH环境变量

安装好后，要检查PATH变量是否存在MongoDB安装的bin目录，
 
如`C:\Program Files\MongoDB\Server\3.0\bin`如果不存在，则需要手动将目录添加到系统PATH变量中

同时注意，如果不重启机器的话，PATH变量还没生效，需要在命令行窗口，执行
``` 
Set Path=%path%;C:\Program Files\MongoDB\Server\3.0\bin
```
注意，=号两边没有空格

### 安装后指定数据库创建目录

**安装后不要马上执行**，要先指定目录。  
比如在C盘创建 Data 目录，并在该目录下再建db和log目录，如：

```
c:\Data\db
c:\Data\log
```

或者在C盘创建 MongoDB 目录，并在该目录下再建db和log目录，如：

```
c:\MongoDB\db
c:\MongoDB\log
```

然后执行以下命令：  

```
mongod --dbpath "c:\Data\db" --logpath "c:\Data\log\mongodb.log"
或
mongod --dbpath "c:\MongoDB\db" --logpath "c:\MongoDB\log\mongodb.log"
```

> *注意：* logpath是要指定文件名才可以


### 启动数据库命令：mongod 

指定目录时，执行的mongod命令就是启动数据库命令，

下次开机运行时，要重新启动数据库，分两种情况：

- 如果是数据目录为`c:\Data\db`,则直接用mongod命令即可启动，因为mongoDB默认目录用`c:\Data\db`

```
mongod
```

- 如果目录不是`c:\Data\db`，则要完整指定数据库目录才能启动，如：

```
mongod --dbpath "c:\MongoDB\db" --logpath "c:\MongoDB\log\mongodb.log"
```

执行后，显示 `wait....`, 表示成功，**不要关掉该窗口**。

### 命令行工具命令：mongo

启动数据库后，**不要关掉该窗口**,重新打开另一个命令行窗口，使用`mongo`命令，进入MongoDB命令行状态。可按<kdb>Ctrl+c</kdb>退出。

### 安装可视化工具 Robomongo

对初学者，可以先使用可视化工具操作数据库即可，不需要记太多命令。
Robomongo是免费软件

安装文件：Robomongo-0.8.5-i386.exe  
[Robomongo官网](http://www.robomongo.org/)

可以在Robomongo中练习mongodb命令

### 建立mongodb自启动服务

如果不想每次开机，均要手动运行mongod命令，可在命令行窗口，使用以下命令

在刚才创建的目录，如 c:\Data 或 c:\MongoDB 新建 mongod.cfg 文件。
文件内容为：

**注意：** 命令行窗口一定要用 **管理员** 身份打开。


```
logpath=c:\data\log\mongodb.log
dbpath=c:\data\db
```

或

```
logpath=c:\mongodb\log\mongodb.log
dbpath=c:\mongodb\db
```

**创建服务**

```
mongod --config "C:\data\mongod.cfg" --install
```
或

```
mongod --config "C:\MongoDB\mongod.cfg" --install
```

**启动服务**

```
net start MongoDB
```

**删除服务**

```
mongod.exe --remove --serviceName "MongoDB"
```

> 安装服务可能出现的问题
> 
> - 出现拒绝访问的信息  
>>   把数据库目录，如 `c:\mongodb\db` 下的文件全部删除，重新安装服务。
> - 在服务管理器找不到服务  
>>   没有以管理员身份打开命令行窗口 

### 对初学者学习MongoDB的建议

 - 传统开发者一般比较熟悉SQL类型数据库，对NoSQL数据库不了解，因此首先要了解这两类数据库的主要差异
 - 先初步了解`集合`与`表`，`文档`与`行`概念的差异，初步了解一下简单查询及增删改的命令形式即可
 - 然后以学习 `mongoosejs` 为主，在熟练掌握`mongoosejs`之后，再进一步去学习MongoDB的概念

### 学习资源
- [MongoDB 教程](http://www.runoob.com/mongodb/mongodb-tutorial.html)
- [Mongoose学习参考文档――基础篇](https://cnodejs.org/topic/504b4924e2b84515770103dd)
- [Node+Mongoose常用查询中文文档](http://www.nonb.cn/blog/nodejs-mongoose-query-chinaese.html)

## 4 编辑器 Sublime Text 3

安装文件：Sublime Text Build 3083  

- 传统开发者比较习惯在IDE环境下开发，但前端开发则常直接使用编辑器开发。  
- `Sublime Text 3` 是目前最流行的编辑器，操作快捷，上手也比较快。  
- 尽管还有其它编辑器，但建议先熟练掌握`Sublime Text 3`之后，再考虑是否需要更换。  
- `Sublime Text 3`可以无限期免费使用，会弹出提示购买，[ESC]取消即可，不影响使用。  
 
### Sublime Text 3 插件管理器

[插件管理器官网](https://packagecontrol.io/installation)

安装插件管理器的代码，使用“查看”菜单的`打开面板`命令，或用[Ctrl+`]，输入以下代码， 
并回车，即可安装插件管理器。

```py
import urllib.request,os,hashlib; h = '2915d1851351e5ee549c20394736b442' + '8bc59f460fa1548d1514676163dafc88'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)   
```

插件管理器安装好后，打开命令面板，输入`pci`找到`Package Control:Install Package`命令即可。

### Sublime Text 3 学习建议

**不要在使用前刻意记忆快捷键**

网上有很多关于Sublime的技巧，会涉及很多快捷键，这对初学者有些误导，以为需要记住这些快捷键才能用Sublime，正确的方法是先使用菜单使用这些功能，这些菜单一般为“编辑”、“选择”、“查找”这几个，在使用菜单，慢慢去熟悉快捷键。

**对插件的快捷键也不需要刻意记忆**

当插件越装越多，所涉及的快捷键也越来越多时，也不需要刻意去记忆快捷。只需要先使用命令面板进行调用，`Ctrl+Shift+P`可以调出命令面板，或在“工具”菜单调出命令面板。每次安装插件后，都调出命令面板，看一下插件有没有在命令面板增加命令。

**掌握多光标编辑操作模式**

这是sublime比较有特色的编辑模式，在掌握基本操作之后，要深入了解该模式的使用方法。


### Sublime Text 3 常用快捷键

[常用快捷键中文网页版win+mac](http://sublime.emptystack.net/)  
[动画演示 Sublime Text3 非常有用的快捷键](http://www.kuqin.com/shuoit/20141111/343163.html)

### Sublime Text 3 常用插件

<table>
  <tr>
    <th>插件名称</th>
    <th>插件用途</th>
    <th>备注</th>
  </tr>
  <tr>
    <td>Emmet</td>
    <td>代码生成器</td>
    <td>安装该控件需要注意，网速如果有问题，<br/>可能安装失败主要原因是PyV8的问题</td>
  </tr>
  <tr>
    <td>HTML-CSS-JS Prettify</td>
    <td>代码格式工具</td>
    <td></td>
  </tr>
  <tr>
    <td>jsFormat</td>
    <td>代码格式工具</td>
    <td>另一个代码格式工具，专门处理js</td>
  </tr>
  <tr>
    <td>SublimeCodeIntel</td>
    <td>代码补全</td>
    <td></td>
  </tr>
  <tr>
    <td>ConvertToUTF8</td>
    <td>中文乱码解决</td>
    <td>Sublime只使用UTF-8编码，其它编码的中文均会乱码，<br/>可用这个插件解决</td>
  </tr>
  <tr>
    <td>Monokai Extended</td>
    <td>语法高亮主题</td>
    <td></td>
  </tr>
  <tr>
    <td>Theme - Soda</td>
    <td>颜色主题</td>
    <td></td>
  </tr>
  <tr>
    <td>ColorPicker</td>
    <td>颜色拾取器</td>
    <td></td>
  </tr>
  <tr>
    <td>SideBarEnhancements</td>
    <td>侧边栏增强</td>
    <td></td>
  </tr>
  <tr>
    <td>SyncedSideBar</td>
    <td>侧边栏显示优化</td>
    <td></td>
  </tr>
  <tr>
    <td>BracketHighlighter</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>DocBlockr</td>
    <td>注释生成工具</td>
    <td></td>
  </tr>
  <tr>
    <td>SublimeLinter</td>
    <td>代码规范检查</td>
    <td>代码规范检查框架，具体规范哪种语言，还需要分别安装具体语言包</td>
  </tr>
  <tr>
    <td>SublimeLinter-jshint</td>
    <td>代码规范检查-js</td>
    <td>注意，要生效还是用<a href="#jshint">npm 全局安装 jshint</a></td>
  </tr>
  <tr>
    <td>JS Snippets</td>
    <td>代码片断</td>
    <td></td>
  </tr>
  <tr>
     <td>JavaScript & NodeJS Snippets</td>
     <td>代码片断</td>
     <td></td>
   </tr>
   <tr>
     <td>Emmet Css Snippets</td>
     <td></td>
     <td></td>
   </tr>
   <tr>
     <td>Bootstrap 3 Snippets</td>
     <td></td>
     <td></td>
   </tr>
   <tr>
     <td>Bootstrap 3 Jade Snippets</td>
     <td></td>
     <td></td>
   </tr>
   <tr>
     <td>AngularJS</td>
     <td></td>
     <td></td>
   </tr>
   <tr>
     <td>AngularJS Snippets</td>
     <td></td>
     <td></td>
   </tr>
   <tr>
     <td>JsFormat</td>
     <td></td>
     <td></td>
   </tr>
   <tr>
     <td>OmniMarkupPreviewer</td>
     <td>md实时预览</td>
     <td></td>
   </tr>
   <tr>
     <td>MarkdownEditing</td>
     <td>md编辑增强</td>
     <td></td>
   </tr>
   <tr>
     <td>ExpressComplete</td>
     <td></td>
     <td></td>
   </tr> 
</table>


- Emmet安装不成功的问题，可参照以下几种方法  
    + [Sublime报please wait a bit while pyV8 binary](http://jingyan.baidu.com/article/aa6a2c14d5177f0d4d19c45f.html)  
    + [sublime text3中emmet pyv8安装失败](http://www.cnsecer.com/4112.html)  
    + [手动安装Emmet](http://www.cnblogs.com/tinyphp/p/3217457.html)  

- 中文乱码的问题
    + 要养成习惯，做为前端开发，总是使用utf-8编码

### sublime 打开中文文本要注意的事项

使用 `ConvertToUTF8` 插件后，会将乱码转成中文，但要注意：

- 如果文件比较大，转换要一定时间，没有转换完成，**不要做任何操作**
- 转换成功后，注意观察状态栏，会提示当前编码为 `GB2312`
- 使用`文件/Set File Encodeing to`，选择 `UTF-8`，再保存即可将文件转为`UTF-8`格式
- **注意**：一定要转换成功后，才能做以上操作，如果还是乱码，不要操作。


## 5 Markdown 标记语言 

### 为什么要用Markdown

现在前端开发，普遍使用Markdown文档格式，进行交流。  
Markdown文档书写简单，格式美观，特别是对涉及有代码内容时支持比其它格式更好。  
另外由于Markdown文件本身是纯文本，进行git版本管理也非常方便。

### 如何快速学习

书写Markdown其实不需要特殊学习，先看一下标准样例，然后再了解一下简明语法即可。  

**最好的前端Markdown样例：** [jquery README.md](https://github.com/jquery/jquery/blob/master/README.md)

简明语法可以看这篇文章：[Markdown，你只需要掌握这几个](http://www.tuicool.com/articles/fmeMbqR)  
详细语法可以看这篇文章：[Markdown 语法说明 (简体中文版)](http://wowubuntu.com/markdown/index.html)


### 用什么编辑器最适合

尽管有很多可视化的Markdown工具，不过其实用处并不大，工具栏对于首次书写Markdown有用之外，
其它情况就不会再需要。

另外可视化工具一般有双屏实时显示效果功能，这个功能其实也只是对初写Markdown时，有些用处。
当已经熟悉Markdown的人是不需要的。

因此，笔者根据自己的经验认为，最适合的Markdown编辑器，还是`Sublime Text`，不过需要配合
`MarkdownEditing`和`OmniMarkupPreviewer`、再加上`Monokai Extended`插件这几个插件。

其中`OmniMarkupPreviewer`可以实时在浏览器预览，不关闭浏览器，在`Sublime Text`修改md文件后
浏览器就会自动刷新。

`MarkdownEditing`自带的颜色主题，用起来并不舒服，可以改成`Monokai Extended`的主题，
在`preferences/Package Settings/Markdown Editing`的`Markdown GFM Settings - User`,
设置如下：

```json
{
  "extensions":
  [
    "md",
    "mdown",
    "markdown"
  ],
  "color_scheme": "Packages/Monokai Extended/Monokai Extended.tmTheme",
}
```

### 关于GFM

**GFM**: [GitHub Flavored Markdown](https://help.github.com/articles/github-flavored-markdown/),
特指gitHub上使用的Markdown语法和渲染模式。

### 学习资源

[sublime MarkdownEditing插件使用说明](http://lucifr.com/2012/07/12/markdownediting-for-sublime-text-2/)

### 建议的规范

- **一级-六级标题**：在标题前用`# 标题 ## 标题 `形式。  

    > *注意：*一级标题与二级标题不用`=== 和 ----`，原因是`Sublime Text`的`Ctrl+R`(转到符号)功能不支持这种标题形式
 
- **加粗**：用`**文本**`  
- *斜体*：用`*文本*`  
- **长文字换行**：在上行文字结尾增加两个半角空格
- **长文字分段**: 在上行文字下面空一行

    > *注意：*大段文字，如果没有特殊需要，不需要特殊处理格式，上面是指要强制换行和分段的情况。
    > 强制换行还有一种情况，就是正常换行，但又不想加空行，一般就是每行文字都很短的情况，需要在上行文字结尾增加两个半角空格才能实现换行。

- **列表**：一般使用无序列表，用 ` - 列表文字`  
- **表格**：表格建议使用html标签`<table></table>`实现，`|`方式的表格只有文字很少的情况才适用，因为列文字不一致时且很长时，在编辑器格式比较难看。  
- **引用**：`> 引用`这种格式，如果按原本处理引用文字的本意，没有太多适用的场景，根据实际经验，可以把这种格式用于**提醒注意**这类文字。如：

    > *注意：* 这行文字的格式是扩展了 `>` 引用的意义。 

- **标题**：标题一般不要加章节号，直接用文本标题，如果要使用，仅用在1级或2级标题上。

## 6 浏览器

浏览器一般建议以[Firefox 火狐浏览器](http://www.firefox.com.cn/)为主要工具，
兼用[谷歌浏览器](http://rj.baidu.com/soft/detail/14744.html?ald)。因为谷歌浏览器的开发者工具有些特色功能有时会用到。但谷歌浏览器安装插件因国内网络原因不是很方便。

### Firefox 火狐浏览器常用开发插件

- FireBug 
- Web Developer

## 附件

[第1讲 Sublime Text 3 用户配置和插件配置.md]<https://github.com/qingfeng365/Front-endDevelopmentTraining/blob/master/%E7%AC%AC%E4%B8%80%E5%AD%A3/%E9%99%84%E4%BB%B6/%E7%AC%AC1%E8%AE%B2%20Sublime%20Text%203%20%E7%94%A8%E6%88%B7%E9%85%8D%E7%BD%AE%E5%92%8C%E6%8F%92%E4%BB%B6%E9%85%8D%E7%BD%AE.md>
