---
layout:     post   				    # 使用的布局（不需要改）
catalog: true
title:      显微镜使用笔记 				# 标题 
date:       2020-06-15 				# 时间
author:     麻辣小龙猫 						# 作者
categories: 科研 						
tags:								#标签
    - 显微镜
    - 实验方法
    - 共聚焦
    - 支离破碎旧笔记
---
显微镜有7种成像（明场BF、暗场DF、相差PH、微分干涉DIC、偏光POL、浮雕相衬RCHMC、荧光FL），除荧光之外都要调科勒照明。
<br>

<!-- more -->

## 科勒照明

<br>
视场光栅是下面的那个（这个要动），聚光镜上那个是孔径光栅（这个不动）
<br>
保证明场，注意ph应在4or5空位。<br>
10x（黄色），调焦，视场光栅调小，移动聚光镜高度旋钮使得边缘最清晰：此时达到共轭面。<br>
再到光斑内接以确认在中间，不在中间的话，用螺丝这样调整。再把光栅调到最大，注意激光器位置：光均匀。<br>

## 各种成像模式的设置方法
### DIC
4部件：棱镜x2（分光） 两片偏光镜（起偏 减偏）顺序：起棱棱解。<br>

先调光路再找焦：<br>
* 取下样品
* 10x
* 下面棱镜抽出来
* 点屏幕搞定3块镜（顺序：起偏、上棱镜、减偏（这块在荧光光路epi里）
* 正交位：取走目镜，能看到黑线（看到后把下面棱镜推进去），看不到调上面棱镜
* 在看样品的时候（调焦完之后）调下面棱镜，改变光程差
<br>

### 相差
* 10倍调焦，ph对应2，去掉样品和一个目镜，看到很亮一个环（其实是聚光器
* 换上对中望远镜
* 拧到最开，目视镜内缓缓拧进直至清晰，如果歪的话能看见2个环
拧聚光器环上的小螺丝，让亮的环对到灰的环上
<br>

### 荧光

#### 激发光源和荧光的关系
短波长（能量大）--> 长波长（能量小）：<br>
* 蓝👉绿 
* 绿 👉红 
<br>

#### 正置vs倒置
* 活细胞适合 倒置显微镜
* 倒置的工作距离更长 
<br>

#### 步骤
控制器显示屏：<br>u：激发块；<br> f：盒子；<br>u/g/b：激发光色，ub bg gr ；<br>N narrow. W wide. A超级窄 
<br>
* 找焦面和视野（明场，shutter要有光）**z值变小，物镜远离标本，正倒置皆如此。** 找块选颜色。 
* 推拉杆切换镜下or相机 
* 左上角实时观察 
<br><br>
* 摄像控制：调曝光时间（左自动，右自动适配，然后左边微调）**ctrl+h，用红色检查过曝光点，最好的状态是蓝色无所谓，一点点红点**
* 读取设置，保存路径（右上角），选好要拍的通道（采集打勾），右上角开始，就拍了 
* 保存为vsi（原始文件），再另存为tif保存。
**tif含有颜色/标尺信息，然而一般打不开；所以在存tif之前要在vsi上显示信息，看上去是2个**
<br>

### 共聚焦
* 开机顺序：全部硬件打开，然后小电脑，然后大电脑。按数字开也行：显微镜控制器 电动载物台 小电脑 大电脑 psu 汞灯 激光 
* 常用：左上角菜单里5大类  3条光路 
* 明场大致调焦（汞灯 ）换激发光，live再调焦面  

#### 模块： 
左上角：只选最左边的即可 
<br>
左中：曝光时间等，视野尺寸、光学放大等 
<br>
中栏： 
* average可增大信噪比 
* 扫描模式 
* 激光强度 
<br><br>
1 目镜明场焦面 <br>
2 设定左上epi，LSM，中栏选染料，点live，相当于实时曝光，然后对着相机再定焦面 <br>
3 工具栏HiLo图片调稍亮（HV600），稍稍过曝，以减少激光强度，调其他参数，大小等，加标尺 
	* 第一个百分比：激光强度 

	* hv见上文 

	* 不用改gain 

	* offset：一起变暗 

**调不好可能是漂白 **

<br>

右上角start照相，右键输出 

#### 图像质量提升：
亮度对比度，以及 <br>
* 增加点光时间（但不超过8ms） <br>
* 增加扫描分辨率（像素up） <br>
* average降背景噪 <br>
* offset，（类似合并像素，慎用 <br>

 
 

右栏： 

 可以拍录像：每隔xx时间拍一张 

 可以拍3d：设定上下底面 

右上存储路径、右键导出 。图栏工具栏可手动加标尺 。
<br>

 
 

## 图像分析处理ImageJ
* Merge 
* 颜色通道filter 0.3%, 8bit，最后融合 
* 加标尺（没信息的先set scale 

### 定量
* binary（弄完还是8bit ）
* Analyse particles  

