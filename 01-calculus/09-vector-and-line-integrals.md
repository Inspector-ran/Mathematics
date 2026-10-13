# 09 空间向量与曲线曲面积分：沿路径和边界累积

[高数目录](README.md) · [多元函数](06-multivariable.md) · [重积分](07-multiple-integrals.md) · [练习解析](solutions/09-vector-and-line-integrals.md)

## 1. 这章什么时候读

先掌握向量坐标、定积分、偏导数和二重积分。本章属于后续课程内容，第一次学极限时可以跳过。这里提供从参数化到积分的完整起步路线，但不要求第一次就记熟所有空间公式。

学习目标：区分长度累积、做功累积和穿过曲面的通量；会处理线段、圆周、平面等简单对象；使用 Green 或 Gauss 定理前能检查方向与光滑性。

## 2. 向量的点积与叉积分别做什么

对三维向量 $\boldsymbol a=(a_1,a_2,a_3)$、$\boldsymbol b=(b_1,b_2,b_3)$，点积是一个数：

$$
\boldsymbol a\cdot\boldsymbol b=a_1b_1+a_2b_2+a_3b_3
=|\boldsymbol a||\boldsymbol b|\cos\theta.
$$

它能判断垂直：非零向量点积为零时，两者垂直。这里 $|\boldsymbol a|=\sqrt{a_1^2+a_2^2+a_3^2}$ 表示长度。

叉积 $\boldsymbol a\times\boldsymbol b$ 是一个向量；当两向量不平行时，它垂直于两者张成的平面。当两向量平行或其中有零向量时，叉积为零向量，没有确定方向。它的长度等于以两者为邻边的平行四边形面积：

$$
\boldsymbol a\times\boldsymbol b
=(a_2b_3-a_3b_2,\ a_3b_1-a_1b_3,\ a_1b_2-a_2b_1).
$$

交换顺序会反号。以非零法向量 $\boldsymbol n=(A,B,C)$ 和一点 $(x_0,y_0,z_0)$ 描述平面，可以写成 $A(x-x_0)+B(y-y_0)+C(z-z_0)=0$。

## 3. 参数化：用一个变量走完一条曲线

线段从 $(0,0)$ 到 $(1,2)$，可以写成 $\boldsymbol r(t)=(t,2t)$，$0\le t\le1$。$t$ 增大时，点沿指定方向移动。

导数 $\boldsymbol r'(t)$ 是速度向量，其长度 $|\boldsymbol r'(t)|$ 是速率。小时间段对应的小弧长近似为 $|\boldsymbol r'(t)|\,dt$，因此弧长元为

$$
ds=|\boldsymbol r'(t)|\,dt
=\sqrt{(x')^2+(y')^2+(z')^2}\,dt.
$$

圆周 $x^2+y^2=R^2$ 的常用参数化为 $(R\cos t,R\sin t)$，$0\le t\le2\pi$，方向是逆时针。若只取 $0\le t\le\pi$，那只走了上半圆。

## 4. 第一类曲线积分：沿长度累积

设细线上每个位置的线密度为 $f$，总质量对应 $\int_L f\,ds$。参数化后：

$$
\int_L f(x,y,z)\,ds
=\int_a^b f(\boldsymbol r(t))|\boldsymbol r'(t)|\,dt.
$$

例题一：沿从 $(0,0)$ 到 $(1,2)$ 的线段求 $\int_L(x+y)\,ds$。

1. 取 $x=t,y=2t$，$0\le t\le1$。
2. $ds=\sqrt{1^2+2^2}\,dt=\sqrt5\,dt$。
3. 线密度变为 $x+y=3t$。
4. 积分为 $\int_0^1 3t\sqrt5\,dt=3\sqrt5/2$。

换一个方向走同一条线，弧长元仍为非负的长度累积，所以第一类曲线积分不因方向改变而反号。

## 5. 第二类曲线积分：沿方向做功

向量场 $\boldsymbol F=(P,Q,R)$ 沿路径做功可写成

$$
\int_L\boldsymbol F\cdot d\boldsymbol r
=\int_L P\,dx+Q\,dy+R\,dz
=\int_a^b\boldsymbol F(\boldsymbol r(t))\cdot\boldsymbol r'(t)\,dt.
$$

这里用的是速度向量，而不是它的长度。方向反转时，第二类曲线积分会反号。

例题二：$\boldsymbol F=(y,x)$，沿 $x=t,y=t^2$，$0\le t\le1$，求做功。

代入得 $P=t^2,Q=t$，$dx=dt,dy=2t\,dt$。所以

$$
W=\int_0^1(t^2+2t^2)\,dt=\int_0^13t^2\,dt=1.
$$

也可观察 $\boldsymbol F=\nabla(xy)$，势函数沿终点减起点为 $1-0=1$，得到同一结果。势函数存在需要条件；不能把任意场都当成路径无关。

## 6. Green 定理：把闭合曲线换成区域

设平面区域 $D$ 有分段光滑边界，$P,Q$ 在包含 $D$ 及其边界的某个邻域内有连续一阶偏导。正向边界让区域始终在行进方向的左侧：外圈逆时针；若有内孔，孔边界为顺时针。此时

$$
\oint_{\partial D}P\,dx+Q\,dy
=\iint_D\left(\frac{\partial Q}{\partial x}
-\frac{\partial P}{\partial y}\right)\,dA.
$$

例题三：沿单位圆逆时针计算 $\oint(-y\,dx+x\,dy)$。

取 $P=-y,Q=x$，所以 $Q_x-P_y=1-(-1)=2$。场处处光滑，区域面积为 $\pi$，故积分为 $2\pi$。若顺时针，则为 $-2\pi$。

**反例提醒：** 对 $\boldsymbol F=(-y/(x^2+y^2),x/(x^2+y^2))$，零点处场没有定义。即使在其他点算出旋度为零，也不能跨过原点直接应用 Green 定理说绕原点的圆周积分为零。

## 7. 曲面积分与通量：把曲面分成小片

第一类曲面积分 $\iint_S f\,dS$ 按面积累积，与选取法向方向无关。例如密度均匀为 1 时，它就是曲面的面积。

对图形曲面 $z=g(x,y)$，面积元为

$$
dS=\sqrt{1+g_x^2+g_y^2}\,dx\,dy.
$$

第二类曲面积分也叫通量：

$$
\iint_S\boldsymbol F\cdot\boldsymbol n\,dS,
$$

其中 $\boldsymbol n$ 是指定方向的单位法向量。改为相反的法向，通量反号。若图形曲面取向上法向，$\boldsymbol n\,dS=(-g_x,-g_y,1)\,dx\,dy$。

例如水平平面上的单位正方形、向上法向为 $(0,0,1)$，场为 $(0,0,2)$，通量是 $2\times1=2$。若法向向下，结果为 $-2$。

## 8. Gauss 定理：封闭曲面的通量换成体积

若向量场在包含立体区域及其边界的邻域有连续一阶偏导，边界是合适的分片光滑闭曲面，并取外法向，则

$$
\iint_{\partial V}\boldsymbol F\cdot\boldsymbol n\,dS
=\iiint_V \operatorname{div}\boldsymbol F\,dV,
\qquad
\operatorname{div}\boldsymbol F=P_x+Q_y+R_z.
$$

例题四：$\boldsymbol F=(x,y,z)$ 穿过单位球面的外向通量。散度为 3，单位球体积 $4\pi/3$，因此通量为 $4\pi$。

这个方法利用了封闭边界。只给半个球面时，不能直接当作完整球面；通常需要补上底面并计算相应通量，或直接参数化。

## 9. 六道独立练习

1. 求 $(1,2,0)\cdot(2,-1,3)$，解释结果的几何意义。
2. 求 $(1,0,0)\times(0,1,0)$，再交换顺序。
3. 半径为 2 的整圆上，求 $\int_L1\,ds$。
4. $\boldsymbol F=(x,y)$ 沿从 $(0,0)$ 到 $(1,1)$ 的线段做功是多少？反向呢？
5. 用 Green 定理计算边长为 1 的正方形逆时针边界上 $\oint(-y\,dx+x\,dy)$。
6. 用 Gauss 定理求 $\boldsymbol F=(x,y,z)$ 穿过半径为 2 的球面的外向通量。

[逐步答案](solutions/09-vector-and-line-integrals.md)

## 10. 过关标准

看到 $ds$ 知道考虑长度，看到 $dx,dy,dz$ 知道检查方向，看到法向量知道考虑通量。能为简单路径写参数范围，并在使用整体定理前检查区域、光滑性、奇点及取向。
