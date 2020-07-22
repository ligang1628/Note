java jdk 14.0.1 安装教程

## 1、下载安装包
> https://www.oracle.com/java/technologies/javase-downloads.html

## 2、安装jdk
> 安装完成后你会发现该版本是没有 jre 文件的
>> 解决方法
>> 在`jdk`的安装目录下 按 shirt + 右键，选择 `在此处打开Powershell窗口`
>> 执行 `bin\jlink.exe --module-path jmods --add-modules java.desktop --output jre`
>> 来源 `https://blog.csdn.net/xiaoQL520/article/details/88736128`

## 3、配置环境变量

1、右键选择`此电脑`->高级系统设置->环境变量

2、在系统变量中新建 
>	变量名	`JAVA_HOME`
>	变量值	`jdk`的安装目录

3、在系统变量中新建
>	变量名	`CLASSPATH`
>	变量值	`.;%JAVA_HOME%\lib;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar;`

4、选择系统变量Path->编辑->新建
> `win10` => `%JAVA_HOME%\bin` => 上移到第一位
> `小于win10` => `%JAVA_HOME%\bin;`

5、打开命令提示符
> `win+R`输入`cmd`
> `java`或者`javac`
	