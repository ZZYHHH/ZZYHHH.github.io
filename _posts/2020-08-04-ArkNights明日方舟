---

layout: post

title: 'ArkNights明日方舟'

date: 2020-08-04

author: Xena

color: rgb(255,210,32)

cover: '
![image](https://image.baidu.com/search/detail?ct=503316480&z=0&ipn=false&word=%E6%98%8E%E6%97%A5%E6%96%B9%E8%88%9F&step_word=&hs=0&pn=0&spn=0&di=0&pi=100026793308&rn=1&tn=baiduimagedetail&is=&istype=0&ie=utf-8&oe=utf-8&in=&cl=2&lm=-1&st=undefined&cs=&os=&simid=&adpicid=100026793308&lpn=0&ln=2790&fr=&fmq=1596594189508_R&fm=&ic=undefined&s=undefined&hd=undefined&latest=undefined&copyright=undefined&se=&sme=&tab=0&width=undefined&height=undefined&face=undefined&ist=&jit=&cg=brand&bdtype=-1&oriquery=&objurl=https%3A%2F%2Fgss0.baidu.com%2F7LsWdDW5_xN3otqbppnN2DJv%2Fforum%2Fpic%2Fitem%2F7aec54e736d12f2ee585941a58c2d562843568c3.jpg&fromurl=ipprf_z2C%24qAzdH3FAzdH3Fwh_z%26e3Biyrj626yri_z%26e3Bv54AzdH3Ftg1jx&gsm=1000001&rpstart=0&rpnum=0&islist=&querylist=&force=undefined)'

tags: game

---



> 明日方舟的很多设计思路还是很有参考价值的



# 游戏简介 Introduction

Arknighs是一款塔防策略游戏，集合角色收集、养成、轻剧情于一体。游戏世界观建立文明与灾难并存的泰拉世界，玩家将扮演罗德岛机构的一位博士同指挥官，与罗德岛领导人阿米娅一起，对抗天灾和感染者，为世界带来新的秩序。基于这个背景，游戏的美术风格偏向于现代科技感和极简一些，下面会从小到控件，大到框架的角度来给予分析。


# 细节处的文章 Details

Arknights有很多控件都做得蛮有新意，但又融合得很好，有种“润物细无声”的意味。

1. 搜索框，点击搜索框本身时，搜索框背景虚化，整个搜索相当于单独的浮层弹出，让视线更聚焦于搜索结果本身。
![image]('https://github.com/ZZYHHH/PictureHub/raw/master/Arknights/search.jpg')
![image]('https://github.com/ZZYHHH/PictureHub/raw/master/Arknights/search2.jpg')

2. 干员筛选
将常用筛选暴露在外头，而详细的筛直接选用了弹窗形式
![image]('https://github.com/ZZYHHH/PictureHub/raw/master/Arknights/filter.jpg')

3. 物品tips
在弹出tip时，保留了原物品的icon和位置，icon会在原层级上再浮现一层，减少了“弹窗”的中断感，保证了操作的连贯性，这也是保留UI元素的体现之一；tip是可滚动的，减少所占屏幕的空间。
![image]('https://github.com/ZZYHHH/PictureHub/raw/master/Arknights/tooltip.jpg')

4. 列表
明日方舟中，很多界面采用横向排布列表，左右滑动。基于全面屏的趋势，手机长度更长，横向的、占满屏幕长度的列表具有更优的滑动体验。
![image]('https://github.com/ZZYHHH/PictureHub/raw/master/Arknights/list.jpg')


# 有点意思的界面 UI

两个概念

## 自然场景UI
自然场景UI，即与场景相融合的界面元素，常见于一些主机游戏、3A游戏，做个系统的概括：
![image]('https://github.com/ZZYHHH/PictureHub/raw/master/Arknights/UI.jpg')

* Diegetic Interface：A diegetic interface is when a game's interface elements exist In-Universe; 
the Player Character sees them, rather than just the player ("Diegetic" meaning "within the 
narrative", such as diegetic music).
在游戏中的表现，根据载体的类型分类，主要分为三类：可穿戴载体（手环、地图、手表、头显、电子眼、背包、类pad）、固定载体（房子、营地、帐篷）、可移动载体（载具、马匹）、其他载体（异度空间）

* Non-diegetic （非叙事性UI）
绘制在游戏外了，它只能被现实中玩游戏的玩家看到或者听到了，基本上就是用来显示某些相关信息的，这种UI可以与游戏故事和游戏物品完全无关，可以有自己的美术风格。UI的美术风格与游戏风格相近

* Spatial（空间UI）
这种UI在游戏当中主要以3D的形式呈现，他们与游戏环境中的物品相结合，以强化玩家体验，防止他们因跳到菜单页面而破坏沉浸感。这些元素越遵守游戏故事的规则，它们对沉浸感强化的帮助就越大

* Meta（元UI）
存在于游戏故事当中的，但当不存在于游戏世界中时，为亚呈现表现（Meta 
Representations）。亚呈现指的是可以存在于游戏世界中，但不一定能引发玩家形象化空间感的呈现内容。2d的提示等。

## 类 Fluent Design
<u>https://zhuanlan.zhihu.com/p/26925463</u>：
整个设计风格被拆解成以下五个方面：Light 光线，Depth 深度，Motion 动作，Material 材质，Scale 比例。通过 Specs 指引，在视觉上的本质表现是对「拟物」的简化，核心是「质感」。

上述的两个概念是明日方舟界面应用的原则。举几个栗子。

1. 首先，不得不说就是主界面，视觉上是伪3D的界面，UI可以跟着手机陀螺仪呈现轻微的晃动
![image]('https://github.com/ZZYHHH/PictureHub/raw/master/Arknights/main.jpg')
附于界面上的弹窗，很巧妙，减少中断感，与底部界面有一些重复的信息。
![image]('https://github.com/ZZYHHH/PictureHub/raw/master/Arknights/main2.jpg')

2. 在宿舍装扮中，巧妙的设计了2D视角和3D视角的切换。当点击平面的物体时，保留2D视角，当选中立体的物品时，则会切换成带俯视的3D视角，方便用户进行修改、拖动、放置。同时家具上会显示长宽参数，如果与其他物品重叠时，会将重叠的部分红区提示。
![image]('https://github.com/ZZYHHH/PictureHub/raw/master/Arknights/home.gif')
 
3. 弹窗的设计充分考虑了用户的操作性。按钮铺满屏幕长度，增大按钮区域，双手持机点击很便利；没有采用传统的黑屏遮罩，而是将背景虚化以突出弹窗内容；确认和取消按钮用颜色做了强区分。
![image]('https://github.com/ZZYHHH/PictureHub/raw/master/Arknights/popup.jpg')

4. 弱切换/跳转
在很多页面的跳转上都能做到保留上个界面的某些元素，以此弱化界面间的生硬切换。
如干员立绘的适当位移，腾出空间给新界面的组件。这样做的好处有：使界面切换丝般顺滑的同时减少了玩家在新页面弹出的抗拒感。
![image]('https://github.com/ZZYHHH/PictureHub/raw/master/Arknights/offset.gif')






