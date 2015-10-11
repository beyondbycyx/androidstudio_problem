# androidstudio_problem
androidstudio使用过程中的问题，第三方库使用配置问题



###1. 导入androidstudio project时，一直停留在build  project info 时：

 
 可能是gralde的版本设置，gradle的插件版本设置，android的build-tools版本设置，java版本设置有关，
 请查看“gradle文件详述”进行修改设置

注意：“ sourceCompatibility = JavaVersion.VERSION_1_7”这里不要乱改，否则出现这种错误
“C:\Program Files\Java\jdk1.8.0_20\bin\java.exe'' finished with non-zero exit value 1”



### 2. “Crunching Cruncher ic_launcher.png failed, see logs”出现，无法打开资源的问题，显示出了一个中文的字符串的路径
    
如果将你建的工程放在了一个中文文件夹的目录下，由于中文路径问题，是会导致某些错误，如资源无法打开的错误，

### 3.所有的R变红了

  res文件夹下的资源可能出错了，先clean一下工程，再找res下的错误，一般是xml文件里某个标签写多了一个字母的错误

### 4.Retrolambda 是一个在Android和预JDK8平台上的使用Lambda表达式语法的Java类库 配置时，Error:Execution failed for task : null/jre/lib/rt.jar does not exist, make sure that the environment variable JAVA_HOME

```java
retrolambda {
    jdk System.getenv("JAVA8_HOME") //这是由于，JAVA8_HOME是指向系统的jdk环境变量
    oldJdk System.getenv("JAVA7_HOME")
    javaVersion JavaVersion.VERSION_1_7
}
```

所以要去配置好所以要去配置“JAVA8_HOME”，“path”，“classpath” ，可网搜下教程，android studio的sdk location那里也有配置Java jdk的路径选项
