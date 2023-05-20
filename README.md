# Ansys Q3D简介

# 1.Ansys Q3D学生版下载安装

Ansys首页下载学生版：https://www.ansys.com/zh-cn/products/electronics/ansys-q3d-extractor

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/1.png)

进入Ansys官网，点击“学生与学术类”->”点击这里开始“，选择“Ansys Electronics Desktop学生版”下载安装即可。

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/2.png)

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/3.png)

## 2.Ansys Q3D案例

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/4.png)

## 2.1建立导体

选择Q3D Extractor；

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/5.png)

建立导体

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/6.png)

对导体进行命名、材料、颜色、透明度等的修改：

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/7.png)

修改导体位置坐标、长、宽、高、单位等：

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/8.png)

Fit All或快捷键“Ctrl+D”全局显示。

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/8.png)

同理建设第二个导体：

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/9.png)

## 2.2 建立电介质

初始同建立导体一致，区别在于需修改材质：

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/10.png)

选择材质：

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/11.png)

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/12.png)

## 2.3实验

### 2.3.1识别导体

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/13.png)

### 2.3.2分析&添加解决方案设置

右键“Analysis”，添加解决方案配置

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/14.png)

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/15.png)

### 2.3.3验证分析

验证配置全部通过即可开始分析。

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/16.png)

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/17.png)

## 2.4结果

右键“Results”，选择“Solution Date”

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/18.png)

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/19.png)

# 3.电容&自电容&互电容

电容为系统存储电荷的能力，通常可以定义为物体相对于接地参考电位升高 1 伏所需的电荷量。在线性系统中，表达式如下：

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/20.png)

其中 Q 是电荷，V 是对地电位差，C 是电容。

根据定义，即使是单个孤立导体也有电容，它是以相对于无限远的接地球壳定义的。对于导电球体，自电容是

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/21.png)

互电容（也称为寄生电容或杂散电容）是在两个电荷体之间产生的期望的或不期望的电容（电荷积累）。如果将一个带电物体放到另一个物体附近，第一个物体上的电荷分布将因静电感应过程而改变（不要与电磁感应混淆）。特别是在传输系统中，线路之间的电容耦合通常是非预期的，是比较棘手的问题，原因是它会产生噪声。

为方便起见，可以矩阵形式排列一个由 N 个导体和一个附加接地板组成的系统的互电容及Spice 矩阵：

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/22.png)

在场论中，另一种矩阵形式更常见：Maxwell矩阵。因为名称非常相似但系数不相同，所以理解Spice矩阵与Maxwell矩阵之间的关系非常重要。Maxwell矩阵描述了第 i 个导体的电荷与系统中所有导体的电压之间的关系。

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/23.png)

# 4.Maxwell矩阵与Spice矩阵

Spice矩阵和Maxwell矩阵之间的关系如下：

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/24.png)

Maxwell矩阵与Spice矩阵的关系为：对同一个概念使用两个不同表达式表述的结果。

由模拟器生成的矩阵采用Maxwell格式。由于标准Spice元件只有两个端子，因此该软件从Maxwell矩阵电容和电导元素中派生出Spice矩阵格式。

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/25.png)

图余弦波电流激励

对电压系数进行匹配，得到：

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/26.png)
定义：
![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/30.png)
![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/31.png)

由两导体场解的能量Ue计算得到Maxwell电容矩阵方程为:

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/27.png)

自电容(对角矩阵元素)大于零，互电容(非对角矩阵元素)小于或等于零。这是因为从物理上讲，在导体上施加正电压而使其他导体接地会导致正电荷积聚在受激导体上，而在周围导体上形成相应的负电荷。在Maxwell矩阵中，自电容（矩阵的对角线项）指物体的所有互电容之和。



Spice矩阵如下：

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/28.png)

在Spice矩阵中，自电容指物体在无穷远处与参考地V=0的互容。前面导体矩阵的Spice电路等效如下:

![image](https://github.com/WangRui8217/Ansys_Q3D/blob/main/images/29.png)

这个矩阵是对称的。它的对角线分量大于或等于零(如果导体相互屏蔽，它们可能恰好为零)，它的非对角线分量也大于或等于零。

通过公式定义可得：Maxwell矩阵的自容为所有其他导体对本身导体的互容总和；Spice矩阵的自容为导体本身相对于无穷远处的接地端的电容。
