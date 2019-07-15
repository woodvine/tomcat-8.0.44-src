# tomcat-8.0.44-src
Tomcat 8.0.44 Eclipse 编译后的工程，可以直接导入到 Eclipse 或者 IDEA 中。

# 自己编译 Tomcat 的流程
##源码及环境准备
从网上下载tomcat8，具体地址：http://tomcat.apache.org/download-80.cgi，版本：apache-tomcat-8.0.44。
操作系统 win10，编辑器，idea 2016，jdk 7。
Tomcat 7 编译需要使用 jdk 6
 
##源码配置
1.	由于tomcat的源码默认采用ant编译，所以需要本地安装ant 
2.	由于需要导入到idea下，所以在源码的根目录需要创建pom.xml,具体如下：
3.	创建 catalina-home，目前需要与tomcat源码的位置平级，如下：
 
4.	在命令行下，进入到 apache-tomcat-8.0.43-src 下（源码的根目录），运行ant命令
编译之后会在根目录下生成output文件夹，之后将/output/build/ 下的temp、bin、conf、lib、webapps、logs 复制到catalina-home下，需要复制文件见下图：
 
 
 
运行配置
1.	IDEA导入pom.xml 文件，将工程打开。在Run菜单，点Edit Configurations，点“+”，选Applcation，配置如下：
 
在Man class:中填入，org.apache.catalina.startup.Bootstrap
在VM options:中填入，你刚刚设置catalina-home路径，我的是：-Dcatalina.home="D:\rundata\idea_workspace\catalina-home"
Working directory是默认的，不用管
Use class path of module里选择Tomcat8.0，这个和你在pom.xml中的配置有关
JRE，我选择的是1.7
最后点OK。
2.	右上角运行项目里，选择：BootStrap  ，点run 或者run的图标按钮。
 
3.	 在浏览器中输入 localhost:8080  ，效果见下图：
 
 
 
 

