Maven的简单使用
1、是什么：在实际开发项目中，我们可能需要引用外部的许多jar文件，我们之前往往需要将jar资源下载下来，再放在lib文件中，进行引用。
但是一旦学习了后期框架后，每一个框架都需要众多的jar包，jar包之间，可能会有冲突，每一次下载jar包，或者引用都会比较麻烦。（简而言之：一种管理jar包的工具）
仓库分为：中央仓库，本地仓库，第三方仓库
我们也可以自己封装jar包，在别的项目里使用自己封装的jar包也是很nice的（成就感ing）

2、怎么用：（日常百度）
第一件事情： 电脑maven的环境 ：
           1：下载maven，
           2：解压缩
           3： 配置环境变量
           4：cmd看看是否安装成功！  mvn  -v 查看版本
           5： 更改一下本地仓库的位置： 默认在  ${user.home}/.m2/repositoty
                  可以更改： 在settings.xml文件中 设置本地仓库的位置
                  
 3、 可以下用命令行去创建一个maven的  
 java项目
      mvn archetype:generate  : mvn  创建的指令
      -DgroupId=com.fxust        ： 包名：  com.icss.etc
      -DartifactId=demo             ：项目名称： myjava
      -DarchetypeArtifactId=maven-archetype-quickstart ： java普通项目

Web项目
mvn archetype:generate  创建
-DgroupId=com.fxust.codelab   包名：   com.icss.web
-DartifactId=myweb            项目名:  myweb
-DarchetypeArtifactId=maven-archetype-webapp


坐标： 
清理：mvn  clean: 会将原来编译好的target目录下的资源清空
编译  ： mvn compile  ： 将源代码进行编译
测试： mvn  test ：将测试的代码进行编译
打包：mvn  package：将整个项目进行打包：java项目打包成 jar包。web项目打包成war包
将自己的jar项目，导入到本地仓库中： mvn install： 将打包好的jar包安装到本地仓库中


第一步：安装maven ，教程见：
https://www.cnblogs.com/yyiou/archive/2017/08/22/7411409.html
第二步：使用
        Maven是基于坐标管理的！
        坐标的概念是：平面中：x,y两个坐标可以唯一的指定平面的某一个位置。
        Maven也是用坐标的方式来确定某一个jar资源：坐标组成是：
· groupId：组织标识（包名）
· artifactId：项目名称
· version：项目的当前版本
· packaging：项目的打包方式，最为常见的jar和war两种
坐标管理的好处是：
· Maven世界拥有大量构建，我们需要找一个用来唯一标识一个构建的统一规范。
· 拥有了统一规范，就可以把查找工作交给机器。
第三步：创建一个maven项目
      用命令行创建一个maven项目：
     https://www.cnblogs.com/zhangyinhua/p/7512518.html
1： 用命令行创建一个项目，并且打包成jar包，给别人使用
  1： 首先创建一个文件夹 ：
 如： F:\mavenProject
      2：选中文件夹，按住：shift+右键，点击  在此处打开命令窗口
 
3：输入指令： 命令：mvn archetype:generate -DgroupId=com.zyh.maven.quickstart -DartifactId=simple -DarchetypeArtifactId=maven-archetype-quickstart
　　　　mvn：核心命令
　　　　archetype:create：创建项目，现在maven高一点的版本都弃用了create命令而使用generate命令了。
　　　　-DgroupId=com.icss ：创建该maven项目时的groupId是什么，该作用在上面已经解释了。一般使用包名的写法。因为包名是用公司的域名的反写，独一无二
　　　　-DartifactId=demo00：创建该maven项目时的artifactId是什么，就是项目名称
　　　　-DarchetypeArtifactId=maven-archetype-quickstart：表示创建的是[maven] java项目
 
    
     
  
 
   
查看文件夹：生成一个maven项目，src中有源码:App.java文件可以进行编译
  
输入指令：  
注意：使用命令时，必须在maven java项目的根目录下，及可以看到pom.xml
 1： mvn  compile
 2：mvn  test
3： mvn packpage
Maven的组合件：
　5）清理：mvn clean　　　 --删除target目录，也就是将class文件等删除
　　6）部署|发布：mvn deploy　　--将压缩文件上传私服
　　7）组合使用Maven命令
　　　　maven的编译，清理，测试，打包，部署命令是可以几个命令同时组合起来使用的，常用的命令组合如下：
　　　　mvn clean compile（先清理在打包）
　　　　mvn clean install
　　　　mvn clean test
　　　　mvn clean package
可以直接将jar包导入到eclipse中的项目中进行使用！
 
创建一个javawebmaven项目也一样
指令: 1）命令：mvn archetype:generate -DgroupId=com.icss.etc -DartifactId=myweb -DarchetypeArtifactId=maven-archetype-webapp -Dversion=0.0.1-snapshot
 　　　　其他都差不多，创建maven web项目的话 -DarchetypeArtifactId=maven-archetype-webapp 比创建java项目多了一个 -Dversion=0.0.1-snapshot.
　　　　在创建java项目的时候也可以加上这个，如果不写，会默认帮我们加上1.0-snapshot。
 
 
 
 
创建成功！可以看到一个javaWeb项目
 
在eclipse中：
       在myeclipse中：
https://blog.csdn.net/qq781317982/article/details/68935230



 
       在idea中：
 
jar存在的时期：![image](https://github.com/helloworldkitty/mybatis/blob/master/clip_image010ff3cf3ea-eef5-4bbf-b6d5-2fe7a92d4095.jpg)

  
