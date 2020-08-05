---

layout: post

title: 'ArkNights明日方舟'

date: 2020-08-04

author: Xena

color: rgb(0,156,224)

cover: ![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Arknights/cover.jpg)

tags: game

---



> 明日方舟的很多设计思路还是很有参考价值的



# 游戏简介 Introduction

Arknighs是一款塔防策略游戏，集合角色收集、养成、轻剧情于一体。游戏世界观建立文明与灾难并存的泰拉世界，玩家将扮演罗德岛机构的一位博士同指挥官，与罗德岛领导人阿米娅一起，对抗天灾和感染者，为世界带来新的秩序。基于这个背景，游戏的美术风格偏向于现代科技感和极简一些，下面会从小到控件，大到框架的角度来给予分析。


# 细节处的文章 Details

Arknights有很多控件都做得蛮有新意，但又融合得很好，有种“润物细无声”的意味。

1. 搜索框，点击搜索框本身时，搜索框背景虚化，整个搜索相当于单独的浮层弹出，让视线更聚焦于搜索结果本身。
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Arknights/search.jpg)
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Arknights/search2.jpg)

2. 干员筛选
将常用筛选暴露在外头，而详细的筛直接选用了弹窗形式
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Arknights/filter.jpg)

3. 物品tips
在弹出tip时，保留了原物品的icon和位置，icon会在原层级上再浮现一层，减少了“弹窗”的中断感，保证了操作的连贯性，这也是保留UI元素的体现之一；tip是可滚动的，减少所占屏幕的空间。
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Arknights/tooltip.jpg)

4. 列表
明日方舟中，很多界面采用横向排布列表，左右滑动。基于全面屏的趋势，手机长度更长，横向的、占满屏幕长度的列表具有更优的滑动体验。
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Arknights/list.jpg)


# 有点意思的界面 UI

两个概念

## 自然场景UI
自然场景UI，即与场景相融合的界面元素，常见于一些主机游戏、3A游戏，做个系统的概括：
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Arknights/UI.jpg)

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
 [Fluent Design](https://zhuanlan.zhihu.com/p/26925463)
整个设计风格被拆解成以下五个方面：Light 光线，Depth 深度，Motion 动作，Material 材质，Scale 比例。通过 Specs 指引，在视觉上的本质表现是对「拟物」的简化，核心是「质感」。

上述的两个概念是明日方舟界面应用的原则。举几个栗子。

1. 首先，不得不说就是主界面，视觉上是伪3D的界面，UI可以跟着手机陀螺仪呈现轻微的晃动
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Arknights/main.jpg)
附于界面上的弹窗，很巧妙，减少中断感，与底部界面有一些重复的信息。
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Arknights/main2.jpg)

2. 在宿舍装扮中，巧妙的设计了2D视角和3D视角的切换。当点击平面的物体时，保留2D视角，当选中立体的物品时，则会切换成带俯视的3D视角，方便用户进行修改、拖动、放置。同时家具上会显示长宽参数，如果与其他物品重叠时，会将重叠的部分红区提示。
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Arknights/home.gif)
 
3. 弹窗的设计充分考虑了用户的操作性。按钮铺满屏幕长度，增大按钮区域，双手持机点击很便利；没有采用传统的黑屏遮罩，而是将背景虚化以突出弹窗内容；确认和取消按钮用颜色做了强区分。
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Arknights/popup.jpg)

4. 弱切换/跳转
在很多页面的跳转上都能做到保留上个界面的某些元素，以此弱化界面间的生硬切换。
如干员立绘的适当位移，腾出空间给新界面的组件。这样做的好处有：使界面切换丝般顺滑的同时减少了玩家在新页面弹出的抗拒感。
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Arknights/offset.gif)

5. 2D界面的层次感
最前的移动更快，越远的移动越慢，给玩家一种带景深的镜头移动感和视差效果
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Arknights/layes.gif)
再如左上角的返回按钮，层级高于界面，在页面的切换中始终保持不变。

6. 帮助界面
减少了文字堆积带来的阅读障碍，基本采用新手引导的帮助提示，用图形化的、可分页滑动的形式呈现
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Arknights/help.jpg)

其他有意思的界面~

![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Arknights/lot.gif "抽卡")

![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Arknights/skin.gif "杂志感的换肤")
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Arknights/skin.jpg "杂志感的换肤")

![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Arknights/relation.JPG "关系图")

![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Arknights/signup.jpg "签到")

![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Arknights/navigate.jpg "顶部总导航")

![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Arknights/profile.gif "档案的tab")


# 总结

一些不足之处和改进：
1. 没办法对干员进行一键升级，导致干员的升级操作流程较为繁琐
2. 战斗能增加重新开始功能
3. 仓库的位置和样式太弱了，以至于我玩到了中期才发现这个按钮
4. 数字增减控件还是比较的保守，可以有，比如长按连续增加数字，招募干员增加最大最小时间值
5. 可点击按钮需要一定的适应和学习成本，比如打勾的按钮，刚开始完全不知道是可点击的（不过我看在新版本已经改了 勾勾换成了文字“点击领取”）
6. 右侧为按钮的常用区，tip的弹出会挡住按键
7. 物品获取方式的跳转：完成任务后，建议原路返回，不然玩家会忘记目标和初衷
8. 一些列表，领取后会跳回表头，还得再往下翻到当前进度

一些亮点值得学习：
首先就是UI元素的保留，很喜欢这种跳转的处理方式，游戏中很多处细节都有运用这一理念。
其次整个界面风格科技、简约，符合世界观的设定，运用了极简的线条、富有光泽感的图标，透视的面板，都很加分。

本文的分析还是比较肤浅，偶然看到一篇大佬的分享，贴上链接：
[《明日方舟》UI/UX 分析](https://gameinstitute.qq.com/article/10027)

