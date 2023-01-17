---

layout: post

title: 'Painter Series'

date: 2022-12-28

author: Xena

color: rgb(0,156,224)

cover: ![](https://github.com/ZZYHHH/PictureHub/blob/master/PainterSeries/TexturePainter.png)

tags: TA Tool Unity

---



> 干TA一年了，这一年里写了不少Unity工具，本文是一篇Painter系列工具合集，作为记录和总结



# Texture Painter 纹理绘制工具
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/PainterSeries/TexturePainter.png)
这是一个集合了多种纹理绘制的工具，包括了地形Mask图、LightMap、Flowmap等贴图的绘制，方便开发者在Unity中制作和修改美术资产，所见即所得。

## 地形Mask图
地形需要使用RGBA四通道对应四纹理的Shader，通过工具Config适配不同属性名称的Shader。在Mask的页签下，通过切换不同的Splat贴图进行绘制，同时提供了Paint、Fill、Lasso三种不同的绘制模式。
![](https://raw.githubusercontent.com、ZZYHHH/PictureHub/master/PainterSeries/TexturePainter_Mask.gif)

## 地形Lightmap
可以直接绘制地形的光照贴图

## Flowmap
根据鼠标移动方向绘制Flowmap，提供了清除和柔化模式，支持流动反向

## Texture
可以选择物体的贴图进行自由的绘制


# Geometry Painter 摆放工具
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/PainterSeries/GeometryPainter.png)
Geometry Painter摆放工具可以在场景中方便、快速的摆放物体，如种树种草、摆放建筑道具等，可以随机大小、旋转、种类等属性


# Mesh Painter 网格绘制工具
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/master/PainterSeries/meshPainter.png)
这是一个Mesh相关的绘制工具，可以在Unity场景中方便快速的绘制网格顶点色、法线、烘焙AO。不需要在dcc中绘制，节省反复切换查看的时间。

# Mesh Debugger
![](https://raw.githubusercontent.com/ZZYHHH/PictureHub/blob/master/PainterSeries/meshDebugger.png)
这是一个Mesh的调试工具，可以在Unity场景中方便快速的查看Mesh信息，如顶点色、UV、法线等多种属性。