# 腾讯游戏公开课HM2

## 1.作业内容

1. 实现了游戏开始时随机n(Default=6)个方块变为黄金方块，分数为常规方块的两倍(20分)
2. 射击到方块时增加玩家分数，方块缩小y倍。方块再次被射击时消失。
3. 利用UMG实现游戏过程中和结算时UI

## 2.实现方法

1. 游戏开始时为获取方块类的所有Actor，随机选取其中n个更改Material为黄金，同时设置其Score属性为20。其余方块Score属性为10。
2. 玩家射出子弹后进行碰撞检测，如果碰撞物体为方块，为玩家增加对应分数，同时检测方块是否为第一次被射击。如果方块是第一次被射击，缩放为y倍，否则删除方块。
3. 利用UMG显示倒计时和玩家实时分数，倒计时结束时展示结算页面。

## 3.蓝图细节

1. GameMode蓝图启动时修改方块属性![image-20241212183911018](C:\Users\wenzh\AppData\Roaming\Typora\typora-user-images\image-20241212183911018.png)
2. 子弹进行碰撞检测，改变方块状态并给玩家加分![image-20241212183950932](C:\Users\wenzh\AppData\Roaming\Typora\typora-user-images\image-20241212183950932.png)

# 4.视频链接

https://videos-1330197498.cos.ap-beijing.myqcloud.com/HM2.mp4
