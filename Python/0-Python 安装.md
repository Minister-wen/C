# 1. Miniconda vs Anaconda

<img src=".\Pictures\1.PNG" style="zoom:60%;" />

conda: 包管理工具
miniconda:在conda基础上,加入了python的执行环境以及一些基础的库模块
andaconda:包含miniconda的所有东西,一些额外的python模块,还有图形化界面

暂时先用miniconda,暂时不用用户界面,anaconda太慢了,太麻烦了

## conda 和 pip 的不同

pip只能管理模块

conda 可以管理运行环境, 可以管理python模块,甚至可以管理非python非依赖库(non-Python library dependecies).言外之意就是如果有一些非python的依赖库,pip就没办法处理了,但是conda可以管理

conda提供学习环境,让这个虚拟环境可以运行在不同的操作系统,例如windows,linux和macos.Conda同时可以创建\管理和切换不同的虚拟环境



下列说法不正确的是：D
A.pip可以允许在任何环境中安装python包: 
B.conda允许创建虚拟环境
C.cond a允许在cond a环境中安装任何语言包(包括C语言或者python)
Dconda不可以在Anaconda之外使用。不可以使用现有的Python安装， 通过pip安装conda
A pip 允许在不同操作系统上运行python包
C conda可以安装C语言包和其它语言包
D pip也可以安装conda，然后使用





## 下载miniconda

因为从国外下载的miniconda很多包啥的都不一定复合条件,直接从镜像下载吧.

清华的python一直维护的是比较好的,

https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/

ctrl + F 搜索关键词latest,找到最新的conda下载

<img src=".\Pictures\2.PNG" style="zoom:60%;" />

你看到,尽管安装的是miniconda,但安装程序显示还是anaconda,这是没有问题的,这个py后面跟的是conda会自带一个python的运行环境.比如这py11代表会自带一个python 11的运行环境.我们后续可以通过conda再创建其他版本的运行环境

<img src=".\Pictures\3.PNG" style="zoom:60%;" />

不用选环境变量,有需求自己配置,也不要选默认python3.11,因为有的时候可能并不一定要用默认的python

<img src=".\Pictures\4.PNG" style="zoom:60%;" />

## 配置环境变量

配置一个miniconda3的路径和miniconda3\Scripts的路径

验证下 

1. cmd打开,输入conda info,看到信息,就可以了
2. 或者到搜索中,输入anaconda 能看到anaconda prompt应用,输入conda info,能看到信息也算成功

运行 python 

```python
python ./file.py
```
<img src=".\Pictures\5.PNG" style="zoom:60%;" />

conda info 包含的信息：

active environment：当前conda正在管理的环境。默认的环境是base，可以自己创建环境

user cinfig file、populated condig files：配置conda的用户配置文件的目录

channel URLs：conda从哪里找包，一般之后我们会换源，源就包含获取包的网址

envs directiories：目前虚拟环境的目录位置



# IDE（集成开发环境）：Pycharm

## 创建环境

conda要么创建 一个新的环境







# jupyter

Jupyter Notebook是以网页的形式打开，在网页中编写代码和运行代码，代码的运行结果也会直接显示出来

## 第一步：安装

打开anaconda prompt powershell，输入`conda install jupyter notebook`来安装





<img src=".\Pictures\7.PNG" style="zoom:60%;" />

注意，这是在==base==默认环境下安装jupyter notebook。之后在不同的环境中可能需要重复安装jupyter notebook

第二部：启动

切换到想要开发代码的目录，输入jupyter notebook，或者直接搜jupyter notebook 找路径

<img src=".\Pictures\8.PNG" style="zoom:60%;" />

这三个网址都是可以访问的到的



如果要自动打开，

1. 打开cmd，输入jupyter notebook --generate-config，然后能看到这个文件的路径

<img src=".\Pictures\open-1.PNG" style="zoom:100%;" />

2. 输入

   ```python
   # c.NotebookApp.password = ''
   import webbrowser
   webbrowser.register('chrome',None,webbrowser.GenericBrowser(u'C:\\Program Files\\Google\\Chrome\\Application\\chrome.exe'))
   c.NotebookApp.browser = 'chrome'
   
    
       这填浏览器的位置
   ```

   







如果有报错的显示

修改miniconda3/Lib/site-packages/IPyhon/utils/io.py

<img src=".\Pictures\9.PNG" style="zoom:90%;" />



注意事项

jupyter后缀是ipynb,不是py

创建脚本前，一般先切换到相应目录位置，jupyter管理也变无法切换到上级目录



jupyter快捷键



| c                |      |
| ---------------- | ---- |
|                  |      |
| 先点击左侧的框框 |      |
|                  |      |
|                  |      |
|                  |      |
|                  |      |

`ctrl + enter`  执行代码，只执行本单元格的，执行完不会往下执行

shift + enter 执行代码，执行完本单元格，光标跳到下一个单元格（但不执行），如果下面没有，创建一个心的单元格



<img src=".\Pictures\10.PNG" style="zoom:90%;" />

先点击左侧框框，把集中去掉，按b在下方创建新的单元格，按a在上方创建新单元格



jupyter 会默认打印一个单元格的最后一行

<img src=".\Pictures\output-1.PNG" style="zoom:100%;" />



单元格修改时前面的颜色：

绿色框（橙色框）：该单元格处于编辑模式，光标在单元格中，可以输入一些代码

蓝色框：该单元格处于命令行模式，光标不在单元格中了，可以输入一些快捷键，比如a、ctrl enter

<img src=".\Pictures\open-2.PNG" style="zoom:100%;" />

按ESC可以从编辑模式切换到命令行模式；鼠标点入单元格，会从命令行模式变为编辑模式



命令行模式，按m可以将单元格切换为Markdown







