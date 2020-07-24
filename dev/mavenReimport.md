当平台的主项目jar发布为新版本后，引用的平台主项目的其他项目需要reimport来更新为最新的包，操作如下：

打开idea的“Maven Projects”，查看工程的Dependencies，检查对应的平台主项目jar的版本是否为最新版本，如下图：

![mavenReimport.png](../assets/mavenReimport.png)

当前最新版本为1.1.1，则此时还不是最新的，在根项目上单击右键，选择“reimport”即可

![mavenReimport2.png](../assets/mavenReimport2.png)

