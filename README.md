# 抖音数据采集从0到1，安卓App加壳与脱壳原理

前针对移动应用市场上安卓APP被破解、反编译、盗版丛生的现象，很多APP开发人员已经意识到保护APP的重要性。而对于移动应用APP加密保护的问题，如何对DEX文件加密尤为重要。

### 简介
加壳是在二进制的程序中植入一段代码，在运行的时候优先取得程序的控制权，做一些额外的工作。大多数病毒就是基于此原理。是应用加固的一种手法对原始二进制原文进行加密/隐藏/混淆。<br>作用：加壳的程序可以有效阻止对程序的反汇编分析，常用来保护软件版权，防止被软件破解。<br>APP加壳软件：apkprotect，梆梆加固，爱加密，娜迦，阿里，百度，腾讯，360等<br> 

### Android Dex文件加壳原理
下面是Android加壳的原理：

### ![image.png](https://cdn.nlark.com/yuque/0/2021/png/97322/1610447155773-707b8df0-d021-4e71-b7c3-f9b7756a5d37.png#align=left&display=inline&height=125&margin=%5Bobject%20Object%5D&name=image.png&originHeight=250&originWidth=632&size=11871&status=done&style=none&width=316)

<br>在这个过程中，牵扯到三个角色：<br>1、需要加密的Apk(源Apk)<br>2、壳程序Apk(负责解密Apk工作)<br>3、加密工具(将源Apk进行加密和壳Dex合并成新的Dex)<br> <br>主要步骤：<br>1、拿到需要加密的Apk和自己的壳程序Apk<br>2、用加密算法对源Apk进行加密在将壳Apk进行合并得到新的Dex文件<br>3、替换壳程序中的dex文件即可，得到新的Apk,<br>那么这个新的Apk我们也叫作脱壳程序Apk.他已经不是一个完整意义上的Apk程序了，他的主要工作是：负责解密源Apk.然后加载Apk,让其正常运行起来。<br> <br>在这个过程中我们可能需要了解的一个知识是：**如何将源Apk和壳Apk进行合并成新的Dex**
```python
优点:  1、保护自己核心代码算法,提高破解/盗版/二次打包的难度  
 
       2、还可以缓解代码注入/动态调试/内存注入攻击.
 
缺点: 1、影响兼容性     2、影响程序运行效率.
```

<br>

> 短视频、直播数据实时采集接口，请查看文档： [TiToData](https://www.titodata.com?from=douyinarticle)


<br>免责声明：本文档仅供学习与参考，请勿用于非法用途！否则一切后果自负。
