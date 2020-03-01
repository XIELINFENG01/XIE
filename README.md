# github的学习报告
 
 
 # 第一次学习报告  
* @Author 谢林枫
* @Date 20202.2.2
* [学习内容1](#1) | [学习内容2](#2) | [学习内容3](#3) | [学习内容4](#4)

# <a id='1'>学习内容1</a>
# 初级入门   使用github的目的与其概念
* 目的：借助github托管项目代码；[github官网]（https://github.com/）
* 基本概念：
* 1.仓库repository; 仓库用来存放项目代码，每个项目对应一个仓库，多个开源项目对应多个项目；
* 2.收藏star; 收藏项目方便查找；
* 3.复制克隆项目fork; 点下fork按键相当于深拷贝别人的仓库，在自己账号下生成于这个一模一样的仓库(独立存在) fork from...；
* 4.发送请求pull request; 请求之后新建文件后能进行“合并”；
* 5.关注watch; 更新通知；
* 6.事务卡片issue; 发现bug，未完成；

 # <a id='2'>学习内容2</a>
 # 创建仓库
 * 1.star a project 进入创建库；（一般情况是及时项目名）
 * 2.repository name 填写仓库名称；
 * 3.descrition optional 项目描述；
 * 4.initialize this repository with a REANDE; 在仓库下多一个reande文件说明项目；
 * 5.craete repository;  创建完成；
 # 仓库主页
 * 批注  ![主页批注]（）
 * 可视仓库名,用户名,可新建issue,可通过edit 更改项目描述；
 # 仓库管理
 * creat new file ;新建文件   
   1. name your text;命名文件名称 (注意加后缀名)
   2. edit file;创建文件内容 
   3. preview changes;查看文件更改；
   4. commit file;  下的表单需要填写每次提交的目的，原因：方便其他开发者知道知道本次文件更改的原因；
   5. 创建完文件后，会自动跳转到仓库主页；
 * edit； 编辑修改文件内容 (小笔) 
   1. 方法1.点击文件名到文件详细页可做删除和修改动作；
   2. 方法2.点击文件的详细描述可查看该文件详细的提交信息；
   commit changes;详细记录每次更改；
 * 删除文件
   1. 点击文件名，进入文件详情页；
   2. 点击 垃圾桶 删除，commit changes；
     3. 思考：被删除文件如何查看信息？  （点击 commits 按键查看）
 * 上传文件
   1. choose your file;（一次可上传多个文件）直接拖动文件；
   2. 成功:显示文件夹；
 * 搜索仓库文件 （find file）
   1. 法一：输入文件名称，进行删选；
   2. 法二： （多学一招：快捷键t）
 * 下载/检出项目
   1. 打开项目主页，close or download,download zip
   2. 如果是git，则需要在网址框进行网址点击下载；
 # github issues
 * 作用：发现代码的bug,但是目前没有成型的代码，需要讨论时用；或者使用开源项目出现问题时用；
 * 主页下显示所以的bug或者交流问题的列表；
 * 创建issues；new issues;
   1. 点击issues,文件标题，问题具体描述；
   2. 创建成功后在其他的关注人的问题首页会有相关显示；（可直接进行回复，再关闭issues）
   3. 之后在仓库issues列表中 open or close进行列表来回切换状态；
 # <a id='3'>学习内容3</a>
 # git 初级入门学习
 * 什么是git? (git是一个免费的，开源的版本控制软件)
 * git官网下载：（https://www.git-scm.com/download）；安装；
   安装流程：（稍等）
 # git的工作流程
 * git的工作分区
   工作区|暂存区|git的仓库
  1. 工作区；添加 编辑 修改文件；
  2. 暂存区：暂存已经修改的文件最后统一提交到仓库；
  3. git的仓库：确定文件保存处，成为新版本，他人可观看；
 * 向仓库添加文件的历程
   1. **git status + git add 从工作区到暂存区**；
   2. **git status + commit -m +文件描述 从暂存区到仓库；
   3. **git status + 添加文件**；
# git的初始化和仓库的建立
* git基础设施 （git安装成功后需要完善一些基础的信息设置）
  1. 设置用户名和邮箱**留心：该设置在主页仓库显示是谁最新提交了该文件**
  $ git config --global user.name "Your Name"
  $ git config --global user.email "email@example.com"
* 初始化一个git仓库
  1. 创建文件夹  （**mkdir demo1**）或者右键创建文件夹；
  2. 在文件内初始化git（创建git仓库）(**cd demo1///git init**)或者手动CD到指定的文件夹；（**git init**）
  3. $ git add 文件名
  4. $ git commit -m "描述内容"
  5. 在这个过程中可以使用$ git status查看文件状态
  6. **如果看不见文件，则让电脑显示隐藏文件夹**(文件所在的盘符，点击查看，勾选隐藏文件查看)
* 修改仓库文件
  1. **vi(m)**修改
  2. 仿照仓库添加流程
  3. **git status + git add 从工作区到暂存区**；
  4. **git status + commit -m +文件描述 从暂存区到仓库；
  5. **git status + 添加文件**；
* 删除文件
  1. 公式：**rm +文件名**
  2. 从git中删除文件名：**git rm +文件名**
  3. 提交操作：**git commit -m +提交描述**
# <a id='4'>学习内容4</4>
* git 管理远程仓库
  1. 目的：备份，实现代码共享和远程化管理
  2. 输入指令$ ssh-keygen -t rsa -C "youremail@example.com"
     邮箱要填自己账号绑定的邮箱，
     回车确定，
     这时在用户的目录下会有一个.ssh的文件夹，点开，复制id_rsa.pub文件的内容，
     进入github，点开自己的头像的setting选项，选择SSH and GPC keys 然后新建一个newSSH，输入title，然后粘贴到key的输入框中

