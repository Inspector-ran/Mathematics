# 05 特征值：找到变换中方向不变的向量

[线代目录](README.md) · [上一章：方程组与秩](04-systems-and-rank.md) · [练习解析](solutions/05-eigenvalues.md)

## 1. 前置与目标

先掌握矩阵乘向量、行列式、齐次方程组和线性无关。本章先研究实矩阵及实特征值；实矩阵也可能有非实特征值，这时要在复数范围内讨论。

目标是会求简单方阵的特征值和特征向量，解释它们的几何意义，并判断是否能够对角化。不要只背“解特征方程”，还要知道为什么解它。

## 2. 从一张图的想法出发

矩阵 $A$ 作用在向量 $\boldsymbol v$ 上，通常改变长度，也改变所在方向。如果有一个非零向量，变换后仍落在原来那条过原点的直线上，就可以写成

$$
A\boldsymbol v=\lambda\boldsymbol v,\qquad \boldsymbol v\ne\boldsymbol0.
$$

这时 $\lambda$ 叫特征值，$\boldsymbol v$ 叫对应的特征向量。

- $\lambda>0$：保持朝向，长度乘上 $\lambda$。
- $\lambda<0$：朝向反转，长度乘上 $|\lambda|$。
- $\lambda=0$：整个向量被压到原点。
- 特征向量乘任意非零倍数后，仍是同一特征值的特征向量。

**为什么排除零向量？** 因为 $A\boldsymbol0=\lambda\boldsymbol0$ 对任意 $\lambda$ 都成立，零向量无法识别任何特殊方向。但零可以是特征值，别把两个“零”的角色混在一起。

## 3. 为什么特征值要解行列式

把右边移到左边：

$$
(A-\lambda I)\boldsymbol v=\boldsymbol0.
$$

$A$ 为 $n$ 阶方阵，$I$ 为同阶单位矩阵。我们要的是非零解；齐次方程组存在非零解，当且仅当系数矩阵不可逆。因此：

$$
\det(A-\lambda I)=0.
$$

这叫特征方程。先用它求 $\lambda$，再对每一个 $\lambda$ 单独解齐次方程组。**不能停在求出特征值这一步**，因为方向还需要特征向量来表示。

## 4. 例题一：对角矩阵，直接看方向

设

$$
A=\begin{pmatrix}2&0\\0&-1\end{pmatrix}.
$$

对 $\boldsymbol e_1=(1,0)^{\mathsf T}$，有 $A\boldsymbol e_1=(2,0)^{\mathsf T}=2\boldsymbol e_1$，所以特征值 2 对应横轴方向。

对 $\boldsymbol e_2=(0,1)^{\mathsf T}$，有 $A\boldsymbol e_2=(0,-1)^{\mathsf T}=-\boldsymbol e_2$，所以特征值 $-1$ 对应纵轴方向：长度不变，朝向反转。

用代数检查：$\det(A-\lambda I)=(2-\lambda)(-1-\lambda)$，确实只得到 2 和 $-1$。但向量 $(1,1)^{\mathsf T}$ 变成 $(2,-1)^{\mathsf T}$，不是其数倍，故它不是特征向量。不是每个向量都享有“方向不变”的性质。

## 5. 例题二：完整求解并组装对角化

令

$$
A=\begin{pmatrix}2&1\\1&2\end{pmatrix}.
$$

第一步，求特征值：

$$
\det(A-\lambda I)=(2-\lambda)^2-1
=(1-\lambda)(3-\lambda).
$$

因此 $\lambda_1=3,\lambda_2=1$。

第二步，分别求特征向量。$\lambda_1=3$ 时，

$$
(A-3I)\boldsymbol v=\boldsymbol0
\Longrightarrow -v_1+v_2=0.
$$

所以 $\boldsymbol v=t(1,1)^{\mathsf T}$，特征向量要求 $t\ne0$。取 $\boldsymbol v_1=(1,1)^{\mathsf T}$。

$\lambda_2=1$ 时，$v_1+v_2=0$，取 $\boldsymbol v_2=(1,-1)^{\mathsf T}$。

第三步，把两个独立方向按列放入矩阵：

$$
P=\begin{pmatrix}1&1\\1&-1\end{pmatrix},\qquad
D=\begin{pmatrix}3&0\\0&1\end{pmatrix}.
$$

$AP$ 的两列分别是 $A\boldsymbol v_1$、$A\boldsymbol v_2$，因此 $AP=PD$。两列线性无关，$\det P=-2\ne0$，可左乘 $P^{-1}$：

$$
P^{-1}AP=D.
$$

这就是对角化。$P$ 的列顺序与 $D$ 对角线上特征值的顺序必须对应，不能各排各的。

## 6. 对角化究竟意味着什么

原坐标里变换可能混合不同分量；改用特征向量作为基后，各坐标仅仅独立乘一个数：

$$
A=PDP^{-1}.
$$

右边按作用顺序解释：$P^{-1}$ 把原坐标换到新基，$D$ 对新坐标分别缩放，$P$ 再换回原坐标。

一个 $n$ 阶方阵在所讨论的数域内可对角化，当且仅当它有 $n$ 个线性无关的特征向量。

- 有 $n$ 个互异特征值，一定可对角化。
- 特征值有重根，可能可对角化，也可能不行。
- 判断重根时，要看对应特征空间的维数，而不是只数特征方程的根的重数。

“特征空间”就是 $\ker(A-\lambda I)$，它包含零向量；“特征向量”特指这个空间中的非零向量。

## 7. 例题三：有重根不等于能对角化

取

$$
B=\begin{pmatrix}1&1\\0&1\end{pmatrix}.
$$

特征方程为 $(1-\lambda)^2=0$，所以只有特征值 1，代数重数为 2。继续解：

$$
(B-I)\boldsymbol v=
\begin{pmatrix}0&1\\0&0\end{pmatrix}
\begin{pmatrix}v_1\\v_2\end{pmatrix}
=\boldsymbol0,
$$

得到 $v_2=0$，特征空间只有横轴一维。最多只能找到一个独立特征方向，无法凑成二维的基，所以不可对角化。

反过来，单位矩阵 $I$ 的特征值也只有重根 1，但每个非零向量都是它的特征向量，能找到两个独立方向，因此可对角化。重根本身不是失败原因，独立方向不足才是。

## 8. 用简单关系检查计算

对 $n$ 阶矩阵，在复数范围内按代数重数计数，有：

- 特征值之和等于迹 $\operatorname{tr}A$，即主对角元素之和；
- 特征值之积等于 $\det A$；
- 0 是特征值，当且仅当 $A$ 不可逆。

这些是检查工具，不能代替特征向量计算。特别是三阶以上，只知道和与积通常无法确定全部特征值。

实对称矩阵的特征值都是实数，并且可以正交对角化；下一章用这个性质理解二次型。

## 9. 六道独立练习

1. 求 $\operatorname{diag}(4,-2)$ 的特征值，并各写一个特征向量。
2. 求 $A=\begin{pmatrix}3&1\\0&2\end{pmatrix}$ 的特征值和特征向量，构造 $P,D$ 使 $P^{-1}AP=D$。
3. 对 $A=\begin{pmatrix}2&1\\1&2\end{pmatrix}$，利用分解计算 $A^2$，并用直接乘法检查。
4. 判断 $B=\begin{pmatrix}2&1\\0&2\end{pmatrix}$ 是否可对角化，写出理由。
5. 已知二阶矩阵的特征值是 0、5，它的迹、行列式和可逆性分别如何？
6. 实矩阵 $R=\begin{pmatrix}0&-1\\1&0\end{pmatrix}$ 在实数范围内有没有特征值？在复数范围内呢？用旋转解释实数结论。

[逐步答案](solutions/05-eigenvalues.md)

## 10. 过关标准

能从 $A\boldsymbol v=\lambda\boldsymbol v$ 推出特征方程；能求对应非零向量；能解释列顺序；能用重根反例说明可对角化的真正条件。
