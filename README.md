# SidewalkPaver
+ Pave sidewalks beside a line, and auto place customizable template buildings(trees etc.) on the sideroad.
+ Create, paste, and use a template with just one click.
+ All you operations can be undo and redo.

# 使用方法
> 目前插件整体功能还不是很完善，之后会根据需求来进行完善。

## 模板
### 创建模板
手持金斧头，副手手持骨粉，确保建筑不与任何无关方块相邻（最下面的方块可以接地），然后左键点击要录入的建筑最下面的一个方块，即可完成录入。
### 粘贴模板
手持金斧头，副手手持骨粉，右键点击要粘贴的位置，即可完成粘贴。
### 需要注意的问题 / 可能存在的问题 （更新计划）
1. 模板暂只支持所有方块都直接相连的建筑，其他类型的模板建议使用WorldEdit创建；
2. 暂时无法准确复制和粘贴带有特定朝向的方块（例如南瓜）；
3. 暂时不支持旋转模板；
4. 暂时只支持最大长宽20*20，高50的建筑，超过部分会被截去。

## 铺路
### 使用方法
1. 设定路宽：`/swp set width <路宽>`；
2. 选择起点终点：手持金斧头，左键点击方块以选中起点，右键点击方块以选择终点；
3. 选择路在直线的哪一侧：手持金斧头，面朝所选直线需要铺路的一侧，左键点击空气；
4. （可省略）设定直线材质：即起点、终点所在直线的材质，`/swp set line <材质名称>`，若不设置则默认为SMOOTH_STONE_SLAB；
5. （可省略）设定铺路材质：即要用什么方块来铺路，`/swp set road <材质名称>`，若不设置则默认为SMOOTH_STONE_SLAB；
6. （可省略）设定Marker材质：即在铺路时，遇到什么方块时在此处放置模板建筑物，`/swp set marker <材质名称>`，若不设置则默认为DIAMOND_BLOCK；
7. （可省略）录入模板：详见“模板 - 创建模板”，如果没有设置模板，则Marker会保持原状。
8. 手持金斧头，右键点击空气，执行铺路。

### 需要注意的问题 / 可能存在的问题 （更新计划）
1. 直线必须是独立的一条线段，不能与其他任何方块毗邻（空气除外）。
2. 直线上的拐角处只能有2个方块，不能有三个方块。若直线拐角处如图，则左上角不能有方块；
<img width="64" alt="Screenshot 2022-11-27 at 01 37 57" src="https://user-images.githubusercontent.com/87828006/204101768-691bebcf-f6e1-47f9-a6bd-64a99cee8c37.png">
3. 目前一次任务只支持一个Marker、一个模板，且不支持只对Marker做操作；
4. 目前尚不支持曲线，只支持直线，例如图中绿色部分是受支持的，红色部分是不受支持的；
<img width="217" alt="image" src="https://user-images.githubusercontent.com/87828006/204101908-7c3ced7d-1337-4c25-ae1c-a6ee717a2e8e.png">
5. 铺路任务在服务器主进程同步执行，一次进行太大面积的操作可能导致服务器长时间失去响应甚至崩溃，目前最多支持200格左右长度的直线。

## 撤销和重做
### 使用方法
+ 如果发现做错了，可以使用命令`/swp undo`来撤销上一次操作；
+ 如果撤销之后反悔了，可以使用命令`/swp redo`来恢复上一次操作。
