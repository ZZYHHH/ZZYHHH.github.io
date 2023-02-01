---

layout: post

title: 'Gramophone'

date: 2023-01-17

author: Xena

color: rgb(0,156,224)

cover: ![](https://github.com/ZZYHHH/PictureHub/blob/master/PainterSeries/TexturePainter.png)

tags: TA Maya SubstancePainter Unity PBR

---



> 22年在工作之余，抽空学习了一下全流程，从DCC建模、SP贴图制作、到Shader编写、Unity渲染，感谢同事大佬指点，收获良多。在春节前夕，抽空整理了下整个物件Demo制作过程，以此篇文章稍作记录。


# 前言
这次选取了一个留声机作为制作对象，一个是总体形状虽不复杂但有细节可做文章，一个是硬表面建模符合菜鸟新手入门，于是就从A站中寻找了参考对象，开始中模的搭建...
参考链接 [Gramophone Reference](https://www.artstation.com/artwork/P3AaB)。

# 建模
## 中模与高模
根据参考对象，在Maya中搭建出基本的中模，中模主要注重各结构的比例关系、整体的形状剪影等要素和谐。随后在Zbrush中进行加面细化和纹理雕刻制作出高模。高模对于游戏模型而言，目的虽然仅仅是法线的烘焙，但法线对于材质品质的提升至关重要。因此好的高模是优质法线贴图的基础。下图为在Zbrush细化后的高模：
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Gramophone/HighPolyModel.png)

## 低模与UV
在高模基本搞定后，开始基于高模减面做低模。高到低这个步骤能保证大体的形和拓扑不出错，对于后续法线的烘焙有好处。低模整体控制在3k面以下，秉持每条线都线有所用的原则进行增减。
低模完成后开始展UV，UV的展法也很有学问，需要考虑到AO贴图和法线的展示，哪些单独拆分、如何重叠共用、考虑所占面积、是否打直等等。

## 法线烘焙与AO烘焙
在低模和高模都OK的情况下，我选择了在SP里烘焙法线。这里什么软件不重要，主要选择在MikktSpace的空间下烘焙法线会省事不少。这时候不大需要考虑软硬边的拆分，尽可能全软边烘焙，基本不大出错。这里需要注意UV的修改（移除重叠部分）和零件拆分烘焙（防止Cage框套住其他零件）。最后烘出来的法线和AO贴图不一定尽如人意，还需要在PS里修修补补。
导入低模，贴上法线贴图的效果：
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Gramophone/LowPolyModel.png)

# Shader着色器编写
至此，建模环节基本结束了，整个过程并不轻松，流程复杂，细节繁琐。按理说下一步应该开始绘制贴图，但作为一个TA，怎么说也得自己写一套Shader锻炼下。于是乎先开始shader的编写，再根据开放的属性决定贴图的种类与数量，制作目的性会比较明确。

## Custom PBR Shader
之前对PBR仅停留于表面，这次呢就顺便学习下，自己手撸了一遍PBR Shader，用的渲染管线是Unity的URP。基本的PBR原理和公式在此就不赘述了，看下成果叭：
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Gramophone/CustomPBRShader.png)

Shader的所需的贴图为Albedo贴图、Normal贴图、Mask贴图（R-Metallic，G-Gloss，B-AO，A-Emission）、Cubemap贴图。那么这几张贴图就会作为SP出图的目标贴图了！
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Gramophone/ShaderProperties.png)

## SubstancePainter Shader
由于采用了自定义的shader，SP里头并没有对应的着色器，这个时候就需要手动同步一遍SP的shader，方便后续在sp里头作图所见即所得，不需要在两个软件之间反复横跳。SP的shader采用glsl语言，基于官方给定的Api文档，同步上也困难不大（除了一些小坑）。这个时候我们就获得了Unity和SP同步的效果啦。


# 贴图制作
万事俱备，最后一part就是在Substance Painter里制作贴图。根据上述所需的贴图在sp中备好贴图输出模板。随后分析下材质，金属的有铜、铁等材质，非金属的有木、橡胶、塑料、油漆等材质，基于最底层（基础颜色、粗糙度、金属度）、纹理层（叠加纹理、粗糙度变化）、结构层（叠加AO、曲度）的思路制作。主要原则就是拉开金属与非金属材质的对比，丰富的材质纹理的层次感（增加磨损、脏迹等）。最后模型穿上衣服在Unity中的效果如图：
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Gramophone/GramophoneFinal.png)

# 效果展示
SP和Unity同步的效果图
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Gramophone/UnitySpSync.png)

细节图
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Gramophone/Detail1.png)
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Gramophone/Detail2.png)

动图
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Gramophone/Gramophone1.gif)

![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/Gramophone/Gramophone2.gif)