

# HTML复习

* 新建html文档，输入！然后按Tab生成html框架
* 添加H1、H2等标签
* emmet技巧：
	* "！"+Tab
	* 标签名+Tab
	* ">"标识嵌套
		* ul>li*5
		* table>tr*5>th*4
	* "#"：生成标签并添加id
		* table#products，例如：<table id="products"></table>
	* ".：生成标签并添加类
		* table.products，例如：<table class="products"></table>
	* 邮件超链接：mailto:+邮箱-->
<!--<meta charset="UFT-8">-->

# 动态网站服务器环境

* Internet Information Service (Windows + .Net)
* Apache (Open Source)
* Ngix

## 课程目标

* 部署与管理Moodle开源的学习管理系统（Learning Management System）
* 基于Moddle的优秀网络课程空间创建

# 初步了解WAMP服务器环境

## WAMP是什么

* Windows
* Apache
* MySQL/MariaDB
* PHP /Python

## WAMP的安装

### 手动安装方式

* 先安装Apache，安装PHP组件并修改配置
* 安装MySQL服务器环境
* 安装MySQL的PHP扩展

###利用集成环境

* 集成环境是指将Apache、PHP、MySQL等服务器软件集成成为一个单独的安装包，并包含默认配置
* 常用的集成环境：WampServer、Xampp、Uniserver、EasyPHP等

### 安装WampServer

初始条件

* 安装相应版本VC++可再发行组件包
* 端口不能冲突：80（HTTP）、443（HTTPS）、3306(MYSQL)
	* HTTP协议可被嗅探
	* （HTTP）冲突可能：其他web服务器，如IIS
	* 了解冲突的方法：cmd： netstat -a

软件获取

* 官方下载
* 执行安装
* 启动完成后
	* 绿色：所有服务启动
	* 橙色：至少一个服务未启动
	* 红色：所有服务器为启动
访问与管理

* 访问本机的方法
	* IP地址
	* 主机名（在域中可以用形如www.zjnu.edu.cn的方式，工作组中仅限同组访问，用机器名）
	* 127.0.0.1
	* localhost
	* Wamp根目录：wamp安装目录下的www

使用开源CMS构建网站

* 下载wordpress组件包，解压后放置www目录下
* 加载phpmyadmin，用root登录，创建数据库




	体验moodle的方法
* 官方演示站点
	HTTP://moodle.org 每小时重置
* 自行安装：浙师大moodle一体包
* 自行安装：集成包
* 自行安装：从源码
	首先部署符合条件的wamp环境
	下载源代码（建议下载stable）
	用http://pathtomoodle/index.php 访问，加载安装程序
	说明：事先创建数据库moodle


参考资料：
HTTP://gzs.ilester.net 搜索文章类型moodle

所有的服务器环境默认都有一个web根目录
	wampser：www
	xampp：htdocs

访问规则：

web根目录：
本地：C:\wamp64\www
WEB:http://localhost/

_intro目录：
本地：C:\wamp64\www\_intro
WEB:http://localhost/_intro

wordpress目录：
本地：C:\wamp64\www\wordpress
WEB:http://localhost/wordpress

local:C:\wamp64\www\wordpress


 # 新建数据库的用户名不可以用root，因为如果到时候moodle 被黑了，那你电脑就被黑了，emm
	密码标准：至少8位，要包含大写、小写、数字、符号

 # 语言包的在线安装
	 -site administraction/language/language packs
	 语言包离线下载
	 -http://moodle.org下载语言包
	解压后放在C:\wamp64\moodledata\lang

# 网站管理--外观--主题选择器：为不同类型的设备指定默认主题（默认自带的三个主题：Boost、Clean、More）

# 插件获取
	-http://moodle.org 上插件目录中获取zip文件
	-网站管理->插件->安装插件：上传zip文件并安装
	在线获取插件与安装：
		-网站管理上有一个“从Moodle插件目录安装插件”

# 建立概念
	Moodle中版块、活动类型、主题等等，全是插件

# 实践任务：
-访问http://gzs.ilester.net
	下载往届学生的插件使用汇报，利用插件名称下载并安装符合你的版本的安装包，并试用。

# 修改网站安全策略（密码太复杂）
	网站管理->网站安全设置：修改密码规则（或者禁用密码规则）

# 创建用户
	网站管理->用户->账户->添加用户
	依据网站的安全设置输入用户信息（默认添加的用户没有任何权限）

# 设置用户角色（系统管理员）
	网站管理->用户->权限->网站管理员
	添加或免除需要设置管理员的用户

# 设置用户角色（课程创建者）
	网站管理->用户->权限->系统自带角色
	添加或免除需要设置课程创建者的用户

# 批量导入用户
	创建一个用户信息表（.csv【用逗号隔开】），必须包含的字段：firstname，lastname，email,username，password
	网站管理->用户->账户->上传用户：(注意csv间隔符以及字符编码，一般选择GBK)

# 用上传用户实现批量选课
	创建csv文件：
		基本字段firstname，lastname，email,username，password
		选课字段：course1，type1，group1，course2，type2，group2
		courseN:课程简称
		typeN：1,2,3
		groupN：在课程中创建的小组名
	网站管理->用户->账户->上传用户：设置角色1,2,3代表什么、文件覆盖、添加新用户，更新老用户

# 导航设置
	网站首页的设置
		网站观念里->首页设置，设置登录前后首页显示的信息区块
	导航条的设置
		网站观念里->外观->主题设置：导航菜单中添加菜单项（格式：菜单名|超链接，一行一条，用-表示层级）
# 开启移动终端访问：
		前提：moodle与终端的物理上是连接的
		网站管理->移动应用程序->移动设备设置：开启设置
# 移动APP从哪里获取
-官方moodle mobile 可以从应用市场下载，ios、Android
-Windows 10 系统：也可以下载ump格式的客户端
