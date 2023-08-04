---
{"dg-publish":true,"permalink":"/notes/dot-product/","title":"Dot product","noteIcon":"","created":"","updated":""}
---

点乘我们通常用于衡量两个向量的方向差，或者衡量"做功"的大小，通常我们将它们单位化，然后再计算，这样取值范围就在$-1$到$1$之间，例如两个向量共向，那么值为$1$，反向则为$-1$，垂直为$0$
<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/点乘.78lv308m6p80.webp" width="290"></div>



**代数定义**

两个向量${\displaystyle {\vec {a}}=[a_{1},a_{2},\cdots ,a_{n}]}$和${\displaystyle {\vec {b}}=[b_{1},b_{2},\cdots ,b_{n}]}$的点积定义为
$$\begin{aligned} \vec{a}\cdot \vec{b} = \sum_{i=1}^{n} a_ib_i \end{aligned}$$其中$n$是维度，在2维情况下就是$a_1b_1+a_2b_2$,例如
$$\left ( \begin{matrix} 5_{(a_1)} & 6_{(b_1)} \\ 9_{(a_2)} & 4_{(b_2)} \end{matrix} \right )$$就是$5\times 6+9\times 4$ （这里需要注意与行列式的计算是不一样的，行列式是$5\times 4-6\times 9$）**这里点乘的计算和我们在转置那里讲到的投影是一回事**

**几何定义**
在欧几里得空间中，点积可以直观地定义为
$${\displaystyle {\vec {a}}\cdot {\vec {b}}=|{\vec {a}}|\,|{\vec {b}}|\cos \theta \;}$$
其中$\theta$为两向量之间的夹角

**推导**

两个定义之间是等价的并可以互相推出
根据[[notes/cosine_law\|notes/cosine_law]]余弦定理则我们有
$$|| a-b ||^2 = ||a||^2+||b||^2-2||a||\ ||b||cos\alpha$$展开得
$$\begin{aligned} \sum^{n}_{i=1}(a_i-b_i)^2 =\sum^{i=1}_{n}a_i^2+\sum^{n}_{n=1}b_i^2-2||a||\ ||b||cos\alpha \end{aligned}$$在二维情况下展开有
$$\begin{aligned} (a_1^2+b_1^2-2a_1b_1)+(a_2^2+b_2^2-2a_2b_2) = a_1^2+a_2^2 + b_1^2+b_2^2 - 2||a||\ ||b||cos\alpha \end{aligned}$$消去所有的$a_1^2,\ b_1^2$整理后有
$$-2a_1b_1 + (-2a_2b_2) =  - 2||a||\ ||b||cos\alpha$$两边再同除以$-2$有
$$a_1b_1 + (a_2b_2) = ||a||\ ||b||cos\alpha = \vec{a}\cdot \vec{b}$$ 同样可以推广到$n$维 □

**点乘在投影上的应用**<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/DotProductForProjection.20f8sxq8tejk.webp" width="390"></div>

计算出向量$\vec{b}$在$\vec{a}$上的投影值,则有$||\vec{b}_{\perp}|| = ||\vec{b}||cos\theta$ 