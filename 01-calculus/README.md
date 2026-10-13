# 高等数学：从变化率到累计量

[回到总目录](../README.md) · [使用指南](../START-HERE.md) · [书目对照](../REFERENCES.md)

高数的两条主线是“怎样描述变化”和“怎样累计许多小量”。先学函数与极限，再用导数研究局部变化，用积分研究累计。多元微分与重积分把一个输入扩展到多个输入，级数研究无限相加，微分方程则反过来由变化规律寻找函数。

## 逐章导航

| 章 | 讲义 | 主要任务 | 练习解析 |
|---|---|---|---|
| 01 | [函数、极限与连续](01-functions-limits.md) | 定义域、左右极限、化简、连续性 | [6 题解析](solutions/01-functions-limits.md) |
| 02 | [导数与微分](02-derivatives.md) | 导数定义、求导法则、隐函数、线性近似 | [6 题解析](solutions/02-derivatives.md) |
| 03 | [导数应用](03-derivative-applications.md) | 中值定理、单调极值、最值、洛必达与泰勒 | [6 题解析](solutions/03-derivative-applications.md) |
| 04 | [不定积分](04-indefinite-integrals.md) | 原函数、换元、分部积分、部分分式 | [6 题解析](solutions/04-indefinite-integrals.md) |
| 05 | [定积分与应用](05-definite-integrals.md) | 累计、微积分基本定理、面积、反常积分 | [6 题解析](solutions/05-definite-integrals.md) |
| 06 | [多元函数微分](06-multivariable.md) | 偏导、全微分、梯度、极值 | [6 题解析](solutions/06-multivariable.md) |
| 07 | [重积分](07-multiple-integrals.md) | 区域、累次积分、换序、极坐标 | [6 题解析](solutions/07-multiple-integrals.md) |
| 08 | [无穷级数](08-series.md) | 部分和、敛散判别、幂级数、误差 | [6 题解析](solutions/08-series.md) |
| 09 | [向量与曲线曲面积分](09-vector-and-line-integrals.md) | 参数化、弧长、功、格林公式、通量 | [6 题解析](solutions/09-vector-and-line-integrals.md) |
| 10 | [常微分方程](10-differential-equations.md) | 分离变量、一阶线性、二阶常系数方程 | [6 题解析](solutions/10-differential-equations.md) |

每章先讲符号与条件，再做逐步例题，最后有 6 道独立练习。答案放在另一个文件，先尝试再查看。本目录共 60 道章节练习。

## 哪些必须先会

- 第 01～05 章是一元微积分的主线，建议依次学。
- 第 06 章依赖求导，第 07 章依赖定积分；两者相邻学习有助于熟悉多元函数。
- 第 08 章需要极限、反常积分和泰勒公式；第一次先学常见级数与收敛域。
- 第 09 章需要定积分、参数方程与重积分。第二类积分中的方向尤其需要认真检查。
- 第 10 章在掌握求导和不定积分后就能开始，不必等第 09 章学完。

遇到计算卡住，先回[代数工具箱](../00-foundations/01-algebra-toolkit.md)。遇到 $\forall,\exists,o(x)$ 等符号不熟，先回[数学语言](../00-foundations/02-math-language.md)。

## 动笔时固定检查五件事

1. 对象是什么：数、函数、近似值，还是整个解族？
2. 定义域与区间是什么：分母为零、对数与根式有没有限制？
3. 方法条件满足吗：连续、可导、可积、收敛、方向是否正确？
4. 有没有漏项：链式法则内层导数、积分常数、换元因子、端点？
5. 怎样验证：求导验积分、代回微分方程、比较正负与大小、画区域？

先有这些习惯，再加快计算。复杂题通常会组合几个基础步骤；基础步骤做稳，组合才有意义。

## 本轮暂不要求

不要求刚入门就会所有技巧，也不要求把进阶段落一次看完。傅里叶级数、复杂曲面积分、斯托克斯公式和更多微分方程方法可以依据学校教学要求另增专题。先完成各章“过关标准”，再进入[综合练习](../03-practice/bridge-problems.md)。
