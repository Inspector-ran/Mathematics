# 特征值与对角化：练习解析

[返回本章](../05-eigenvalues.md)

## 1. 对角矩阵

特征方程 $(4-\lambda)(-2-\lambda)=0$，得到 4、$-2$。分别可取 $\boldsymbol e_1=(1,0)^{\mathsf T}$、$\boldsymbol e_2=(0,1)^{\mathsf T}$。任何非零倍数同样可用。

## 2. 上三角矩阵

$\det(A-\lambda I)=(3-\lambda)(2-\lambda)$，特征值为 3、2。

对 3，解 $(A-3I)\boldsymbol v=0$ 得 $v_2=0$，取 $(1,0)^{\mathsf T}$。对 2，得到 $v_1+v_2=0$，取 $(-1,1)^{\mathsf T}$。因此

$$
P=\begin{pmatrix}1&-1\\0&1\end{pmatrix},\qquad
D=\begin{pmatrix}3&0\\0&2\end{pmatrix}.
$$

$\det P=1$，所以可逆。按列检查 $AP=PD$，即可得到 $P^{-1}AP=D$。

## 3. 平方

沿用本章 $P=\begin{pmatrix}1&1\\1&-1\end{pmatrix}$，有 $P^{-1}=\frac12P$，$D^2=\operatorname{diag}(9,1)$。于是

$$
A^2=PD^2P^{-1}
=\frac12\begin{pmatrix}1&1\\1&-1\end{pmatrix}
\begin{pmatrix}9&0\\0&1\end{pmatrix}
\begin{pmatrix}1&1\\1&-1\end{pmatrix}
=\begin{pmatrix}5&4\\4&5\end{pmatrix}.
$$

直接用 $A$ 乘自身，第一行第一列是 $2\cdot2+1\cdot1=5$，第一行第二列是 $2\cdot1+1\cdot2=4$，其余同理。两种算法一致。

## 4. 重根的判断

唯一特征值为 2，代数重数 2。$B-2I=\begin{pmatrix}0&1\\0&0\end{pmatrix}$，所以特征空间为 $\{(t,0)^{\mathsf T}:t\in\mathbb R\}$，维数只有 1。没有两个独立特征向量，不可对角化。

## 5. 迹、行列式与逆

迹为 $0+5=5$；行列式为 $0\cdot5=0$；因为存在零特征值，矩阵不可逆。不要把迹非零误当成可逆条件。

## 6. 旋转与数域

特征方程为 $\lambda^2+1=0$。在实数范围没有解，因此没有实特征值或实特征向量方向。这个矩阵把平面向量逆时针旋转 $90^\circ$，任何非零实向量都不会仍落在原直线上。

在复数范围，特征值为 $i,-i$。例如 $\lambda=i$ 可取 $(1,-i)^{\mathsf T}$，$\lambda=-i$ 可取 $(1,i)^{\mathsf T}$；代入矩阵乘法即可核验。本题是范围意识的拓展，若尚未学习复数，先掌握实数结论。
