# HM1-源码编译UE5及游戏安装包构建

**基本流程：**

1. 加入EPIC组织并从UE5官方的源码仓库fork一份，然后用github-desktop把release分支的仓库clone下来。这一步也尝试了下载zip安装包和直接从终端clone，但是速度都很慢，开了梯1子也只能跑到5MB/S，而github-desktop可以跑到15MB/S
2. 安装VS2022，并根据[官方文档](https://dev.epicgames.com/documentation/zh-cn/unreal-engine/downloading-unreal-engine-source-code#%E4%B8%8B%E8%BD%BD%E6%BA%90%E4%BB%A3%E7%A0%81)选择对应的插件。
3. 在Clone下来的仓库中运行Setup.bat、GenerateProjectFiles.bat得到引擎的`UE5.sln` 文件
4. 在VS2022中对UE5.sln进行build，得到UE5引擎。下面是log：
5. 在引擎中根据TPS模板创建游戏工程，修改工程设置并打包。

**遇到的问题：**

1. 第一次build引擎时速度极慢，build了十几个小时(老是提示Waiting For Memory)，然后新建一个工程时打开不成功，导致我又删了重来
2. 这次参考[UE5编译的提速](https://zhuanlan.zhihu.com/p/720304192)这篇文章，并且多余应用，然后加了20G的虚拟内存，终于在4h内编译成功了。
3. 然后还是出现新建工程打不开，提示`Engine modules are out of date, and cannot be compiled while the engine is running. Please build through your IDE`但是当我打开我的工程的sln文件尝试用VS2022编译后还是报错。
4. 最后参考[How to solve engine modules are out of date](https://forums.unrealengine.com/t/how-to-solve-engine-modules-are-out-of-date/564119)这篇文章，找到DesktopPlatformBase.cpp这个文件然后修改Arguments参数，重新编译引擎，再重新新建工程，这次就OK了，成功打开了模板工程
5. 因为C盘内存不太够了，参考网上的方法把引擎的Cache目录该到了工程的目录
6. 因为没有Android手机，就直接打包桌面版本了，然后打开尝试运行，成功。

**部分截图**：

1. build完成的log![image-20241121154124584](C:\Users\wenzh\AppData\Roaming\Typora\typora-user-images\image-20241121154124584.png)
2. 引擎的初始目录：![image-20241121154245299](C:\Users\wenzh\AppData\Roaming\Typora\typora-user-images\image-20241121154245299.png)
3. 引擎可执行文件目录：![image-20241121154321212](C:\Users\wenzh\AppData\Roaming\Typora\typora-user-images\image-20241121154321212.png)
4. 打包过程的log：![image-20241121154334308](C:\Users\wenzh\AppData\Roaming\Typora\typora-user-images\image-20241121154334308.png)
5. 打包结果：![image-20241121170002364](C:\Users\wenzh\AppData\Roaming\Typora\typora-user-images\image-20241121170002364.png)

