---
{"dg-publish":true,"dg-permalink":"category/basis/","permalink":"/category/basis/","title":"Cosine law","tags":["basis"],"noteIcon":"","created":"","updated":""}
---

余弦定理是描述**三角形中三边长度与一个角的余弦值关系**的数学定理，是**勾股定理在一般三角形情形下的推广**，勾股定理是余弦定理的特例<div align=center><img src="https://cdn.jsdelivr.net/gh/aaronmack/image-hosting@master/mathematics/Law-of-Cosines.46vagpeucam0.webp" width="790"></div>

$$\begin{array}{l}a^2=b^2+c^2-2bc\ cos A \\ b^2=a^2+c^2-2ac\ cos B \\ c^2=a^2+b^2-2ab\ cos C \\ cos A = \frac{-a^2+b^2+c^2}{2bc} \\ cos B = \frac{a^2-b^2+c^2}{2ac} \\ cos C = \frac{a^2+b^2-c^2}{2ab} \\ \end{array}$$

**延伸**

([(-a^2+b^2+c^2)^2](https://zs.symbolab.com/solver/algebra-calculator/%5Cleft(-a%5E%7B2%7D%2Bb%5E%7B2%7D%2Bc%5E%7B2%7D%5Cright)%5E%7B2%7D?or=input))

我们

$$\cos^2 A=\frac{a^4+b^4+c^4-2a^2b^2+2b^2c^2-2a^2c^2}{4b^2c^2} $$

根据

$$\cos^2A+sin^2A=1$$

$$ \sin A=\sqrt{1-\cos^2a}=\sqrt{\frac{4b^2c^2}{4b^2c^2}-\frac{a^4+b^4+c^4-2a^2b^2+2b^2c^2-2a^2c^2}{4b^2c^2}}$$

$$ =\sqrt{\frac{4b^2c^2-(a^4+b^4+c^4-2a^2b^2+2b^2c^2-2a^2c^2)}{4b^2c^2}}$$

$$ =\frac{\sqrt{-a^4-b^4-c^4+2b^2c^2+2c^2a^2+2a^2b^2}}{2bc}$$

三角形面积有

$$\Delta=\frac{1}{2}bc \sin A$$

代入$\sin A$有

$$\Delta=\frac{1}{4}\sqrt{(a+b+c)(-a+b+c)(a-b+c)(a+b-c)}$$ 
(排列组合)