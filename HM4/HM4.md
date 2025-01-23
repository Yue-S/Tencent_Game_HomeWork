# 腾讯游戏公开课HM2

## 1.作业内容

1. 实现登录界面（需要输入用户名和密码，其中密码加密显示，有确认按钮） 
2. 实现加载界面（要有动画表传达正在加载） 
3. 实现射击游戏操作面板（要有血条，子弹数，击中玩家会发生变化的准星

## 2.实现方法

1. 登录界面采用UMG制作UI，对于用户输入的账号信息可以传到服务器，服务器查询已经存在的账户信息获取对应的账户内容。
2. 血条、子弹数涉及到游戏的武器和健康系统设置，方法是把血条等和人物相关的信息存储到PlayerState当中，把UI中的对应变量和PlayerState中的变量进行绑定。而子弹数则是存储到WeaponComponent当中，用户拾取/丢弃武器时修改人物的Current_Weapon变量，再通过这个变量获取子弹等武器相关的信息。

## 3.蓝图细节

1. 玩家拾取武器时更改Weapon变量![](https://image-hosting-1330197498.cos.ap-beijing.myqcloud.com/28794e86-546b-49f6-8a24-9ee247e1417d.png)
2. UI中的变量通过Function绑定到其他类中的对象![](https://image-hosting-1330197498.cos.ap-beijing.myqcloud.com/ba2614a2-5692-40c7-b623-f70749a9d622.png)

# 4.视频链接

https://image-hosting-1330197498.cos.ap-beijing.myqcloud.com/HM4.mp4