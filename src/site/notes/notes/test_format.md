---
{"dg-publish":true,"permalink":"/notes/test-format/","title":"Test format","tags":["basis"],"noteIcon":"","created":"","updated":""}
---


>
## Math
> [!warning] Warning
> 
> Test 
> $$\int_{a}^{b} x^2 dx$$
> Inline $a$
> 

> [!NOTE] 
> 
> DG: Supported, But can't be in the same line, must start another line
> 
> Obsidian: Supported.
> 
> Hugo: Supported.

---
$$
f(n) =
\begin{cases} 
n/2,  & \text{if }n\text{ is even} \\\\
3n+1, & \text{if }n\text{ is odd}
\end{cases}
$$
---
$$
\sum_{k=1}^N k^2
$$
---
$$
\sum^N_{k=1} \color{Lavender}{k^2}
$$
---
> [!NOTE]
> 
>  Hugo: the color not supported. `Lavender`
>  
>  Obsidian: Supported.
> 
>  DG: Supported. [GitHub - oleeskild/digitalgarden](https://github.com/oleeskild/digitalgarden)

---

$$
\left\{\begin{aligned}
3x + 5y +  z \\\\
7x - 2y + 4z \\\\
-6x + 3y + 2z
\end{aligned}\right.
$$

$$
\left(\begin{aligned}
3x + 5y +  z \\\\
7x - 2y + 4z \\\\
-6x + 3y + 2z
\end{aligned}\right.
$$

$$
\left\lbrace \dfrac ab \right.
$$
> [!WARNING] 
> 
> Hugo: Not supported.  `\left\{`, Can use `\left(` or `\left\lbrace`

---
$$
\begin{alignedat}{3}
f(x) & = (m-n)^2 \\\\
f(x) & = (-m+n)^2 \\\\
     & = m^2-2mn+n^2 \\\\
\end{alignedat}
$$
---

$$
% outer vertical array of arrays
\begin{array}{c}
    % inner horizontal array of arrays
    \begin{array}{cc}
        % inner array of minimum values
        \begin{array}{c|cccc}
        \text{min} & 0 & 1 & 2 & 3\\\\
        \hline
        0 & 0 & 0 & 0 & 0\\\\
        1 & 0 & 1 & 1 & 1\\\\
        2 & 0 & 1 & 2 & 2\\\\
        3 & 0 & 1 & 2 & 3
        \end{array}
    &
        % inner array of maximum values
        \begin{array}{c|cccc}
        \text{max}&0&1&2&3\\\\
        \hline
        0 & 0 & 1 & 2 & 3\\\\
        1 & 1 & 1 & 2 & 3\\\\
        2 & 2 & 2 & 2 & 3\\\\
        3 & 3 & 3 & 3 & 3
        \end{array}
    \end{array}
    %
    \\\\
    % inner array of delta values
        \begin{array}{c|cccc}
        \Delta&0&1&2&3\\\\
        \hline
        0 & 0 & 1 & 2 & 3\\\\
        1 & 1 & 0 & 1 & 2\\\\
        2 & 2 & 1 & 0 & 1\\\\
        3 & 3 & 2 & 1 & 0
        \end{array}
        %
\end{array}
$$


---
$$
\mathbf{STUVWXYZ}
$$

## Code 

```python
import os
print("A message")
```


## Other

> [!FAQ]- Closed by default
> Folding/Collapsable callout


> [!NOTE]+ Open by default
> Folding/Collapsable callout

## MathJax / LaTex

[MathJax basic tutorial and quick reference](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference)

$$
\begin{array}{c|lcr}
n & \text{Left} & \text{Center} & \text{Right} \\
\hline
1 & 0.24 & 1 & 125 \\
2 & -1 & 189 & -8 \\
3 & -20 & 2000 & 1+10i
\end{array}
$$

Inline $\sqrt{\mathstrut a} - \sqrt{\mathstrut b}$ formula

$$
\begin{array}{rrrrrrr|rr}
      & x_1 & x_2 & s_1 & s_2 & s_3 &  w &    & \text{ratio} \\ \hline
  s_1 &   0 &   1 &   1 &   0 &   0 &  0 &  8 &            - \\
    w & 1^* &  -1 &   0 &  -1 &   0 &  1 &  4 &            4 \\
  s_3 &   1 &   1 &   0 &   0 &   1 &  0 & 12 &           12 \\ \hdashline
      &   1 &  -1 &   0 &  -1 &   0 &  0 &  4 &              \\ \hline
  s_1 &   0 &   1 &   1 &   0 &   0 &  0 &  8 &              \\
  x_1 &   1 &  -1 &   0 &  -1 &   0 &  1 &  4 &              \\
  s_3 &   0 &   2 &   0 &   2 &   1 & -1 &  8 &              \\ \hdashline
      &   0 &   0 &   0 &   0 &   0 & -1 &  0 &
\end{array}
$$

$$
f\left(
   \left[ 
     \frac{
       1+\left\{x,y\right\}
     }{
       \left(
          \frac{x}{y}+\frac{y}{x}
       \right)
       \left(u+1\right)
     }+a
   \right]^{3/2}
\right)
$$

---

$$0.414213562373095048\approx6\*16^{-1}+a\*16^{-2}+0\*16^{-3}+\cdots$$

$$0.414213562373095048\approx6*16^{-1}+a*16^{-2}+0*16^{-3}+\cdots$$

> [!WARNING] 
> 
> Hugo:  Supported.
> 
> DG: some error. `\*`
> 
> Obsidian: same as DG `\*`

---
$$
\begin{equation}
\begin{split}
(a + b)^3
&= (a + b)(a + b)^2            \\
&= (a + b)(a^2 + 2ab + b^2)    \\
&= a^3 + 3a^2b + 3ab^2 + b^3
\end{split}
\end{equation}
$$

---
$$\boldsymbol{x}$$

---
$$\boldsymbol{x}_{i+1}$$

---

$$
\boldsymbol{x}_{i+1}+\boldsymbol{x}
$$

---
$$\boldsymbol{x}_{i+1}+\boldsymbol{x}_{i+2}=\boldsymbol{x}_{i+3}$$

---
> [!WARNING] 
> 
> Hugo: More than three pairs of braces appear and cannot be displayed

---
$$ \begin{align*} y = y(x,t) &= A e^{i\theta} \\ &= A (\cos \theta + i \sin \theta) \\ &= A (\cos(kx - \omega t) + i \sin(kx - \omega t)) \\ &= A\cos \frac{2\pi}{\lambda} (x - v t) + i A\sin \frac{2\pi}{\lambda} (x - v t) \end{align*} $$

## Misc


<video id="video" controls="" preload="none" poster="视频图片地址"> 
<source id="mp4" src="https://server1.xyzzyxwz.top:12030/res/a.mp4" type="video/mp4">
</video>

<audio id="audio" controls="" preload="none"> <source id="mp3" src="https://server1.xyzzyxwz.top:12030/res/a.mp3">
</audio>​
---

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |


## Symblos

$$
\begin{cases}

\sqsubseteq  \\
{\displaystyle \color {Periwinkle}{\text{Periwinkle}}} \\
{\color{Blue}x^2}+{\color{Brown}2x} - {\color{OliveGreen}1} \\
{\Vvdash \nvdash \nVdash \nvDash \nVDash} \\
{\or \lor \vee, \curlyvee, \bigvee} \\
\blacktriangle, \blacktriangledown, \blacktriangleleft,  \blacktriangleright \\
\sim, \nsim, \backsim, \thicksim, \simeq, \backsimeq, \eqsim, \cong, \ncong \\
\cup, \Cup, \sqcup, \bigcup, \bigsqcup, \uplus, \biguplus \\
\infty, \aleph, \complement, \backepsilon, \eth, \Finv, \hbar \\
\Z \\
\yen \\
\Zeta \\
\zeta \\
\xcancel \\
\widehat \\
\varinjlim \\
\end{cases}
$$

---
$$f(n) =
\begin{cases} 
n/2,  & \text{if }n\text{ is even} \\\\
3n+1, & \text{if }n\text{ is odd}
\end{cases}$$

---



$$
\begin{array}{cc}
\mathrm{Bad} & \mathrm{Better} \\
\hline \\
e^{i\frac{\pi}2} \quad e^{\frac{i\pi}2}& e^{i\pi/2} \\
\int_{-\frac\pi2}^\frac\pi2 \sin x\,dx & \int_{-\pi/2}^{\pi/2}\sin x\,dx \\
\end{array}
$$
---
$$\cancelto{\cancelto{\cancelto{x^{2+x}}{\cancelto{x^2}{x}+4}}4}0$$

$$
\begin{array}{|rc|}
\hline
\verb+\color{black}{text}+ & \color{black}{text} \\
\verb+\color{gray}{text}+ & \color{gray}{text} \\
\verb+\color{silver}{text}+ & \color{silver}{text} \\
\verb+\color{white}{text}+ & \color{white}{text} \\
\hline
\verb+\color{maroon}{text}+ & \color{maroon}{text} \\
\verb+\color{red}{text}+ & \color{red}{text} \\
\verb+\color{yellow}{text}+ & \color{yellow}{text} \\
\verb+\color{lime}{text}+ & \color{lime}{text} \\
\verb+\color{olive}{text}+ & \color{olive}{text} \\
\verb+\color{green}{text}+ & \color{green}{text} \\
\verb+\color{teal}{text}+ & \color{teal}{text} \\
\verb+\color{aqua}{text}+ & \color{aqua}{text} \\
\verb+\color{blue}{text}+ & \color{blue}{text} \\
\verb+\color{navy}{text}+ & \color{navy}{text} \\
\verb+\color{purple}{text}+ & \color{purple}{text} \\ 
\verb+\color{fuchsia}{text}+ & \color{magenta}{text} \\
\hline
\end{array}
$$

---
$$
x = a_0 + \cfrac{1^2}{a_1
          + \cfrac{2^2}{a_2
          + \cfrac{3^2}{a_3 + \cfrac{4^4}{a_4 + \cdots}}}}
$$

$$
\left\langle  
  q
\middle\|
  \frac{\frac{x}{y}}{\frac{u}{v}}
\middle| 
   p 
\right\rangle
$$