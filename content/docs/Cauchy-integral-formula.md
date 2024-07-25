---
title: "コーシーの積分公式"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# コーシーの積分公式

## コーシーの積分公式

コーシーの積分定理から次のコーシーの積分公式を導くことができる。
これは正則関数の性質を調べる上で非常に重要な定理である。
また、コーシーの積分公式は$\delta$関数のようなものと思うこともできる。


{{< hint >}}
    関数$f(z)$が「中心$a$で半径$r$の閉円板$\overline{B_r(a)}$上正則」であり、$z$が円板の内部$B_r(a)$にあるとする。
    このとき
    $$    
    f(z)=\frac{1}{2\pi i}\int_{\abs{\zeta-a}=r}\frac{f(\zeta)}{\zeta-z}d\zeta
    $$
    が成り立つ。

    また、$f$が$D$で正則であり、$z\in\overline{B_r(a)}$で、
    閉曲線$C\subset D$が$D\setminus\{z\}$で$\partial\overline{B_r(a)}$に連続変形可能であるとき、
    $$
    f(z)=\frac{1}{2\pi i}\int_C\frac{f(\zeta)}{\zeta-z}d\zeta
    $$
    となる。
{{< /hint >}}

{{< hint >}}
  $f$を$D$上の正則関数とし、$E$を$D$に含まれる閉円盤、$C$をその境界で反時計回りに向きをつける。
  このとき、任意の$z\in E\setminus C$に対し
  \begin{align*}
    f(z)=\frac{1}{2\pi i}\int_C\frac{f(\zeta)}{\zeta-z}d\zeta
  \end{align*}
  が成り立つ。
{{< /hint >}}

{{< hint >}}
  $$
  \int_C\frac{f(z)}{z-a}dz=\int_C\frac{f(z)-f(a)}{z-a}dz+\int_C\frac{f(a)}{z-a}dz\\
  =\int_C\frac{f(z)-f(a)}{z-a}dz+ 2\pi if(a)
  $$
  であるので、残った積分が$0$であることを証明する。
  $C$のパラメータ表示$a+re^{it}$を用いて
  $$
  \lvert\int_C\frac{f(z)-f(a)}{z-a}dz\rvert
  \leq\int_C\lvert\frac{f(z)-f(a)}{z-a}\lvert\rvertdz\rvert\\
  =\int_C\lvert\frac{f(z)-f(a)}{re^{it}}\rvert rdt\\
  =\int^{2\pi}_0\lvert f(z)-f(a)\rvert dt\\
  \leq 2\pi\sup\lvert f(z)-f(a)\rvert
  $$
  である。
  ここで、コーシーの積分定理によりこの積分は$r>0$に依存せず、
  一方で最後の式は$r\to 0$で$0$に収束するため、積分値は$0$とわかる。
{{< /hint >}}

{{< hint >}}
  $z\in E\setminus C$に対し、
  \begin{align*}
    g(\zeta)=
    \begin{cases}
      \dfrac{f(\zeta)-f(z)}{\zeta-z}&\zeta\neq z\\
      f'(z)&\zeta =z
    \end{cases}
  \end{align*}
  と定義する。

  この$g$は$D$上連続で$\zeta=z$以外では正則である。

  領域に対する適当な条件を考慮することにより、コーシーの積分定理から
  \begin{align*}
    \int_Cg(\zeta)d\zeta=0
  \end{align*}
  となる。
  よって、
  \begin{align*}
    \frac{1}{2\pi i}\int_C\frac{f(\zeta)}{\zeta-z}d\zeta
    =
    \frac{1}{2\pi i}\int_C\frac{f(z)}{\zeta-z}d\zeta
  \end{align*}
  であり、前の計算から
  \begin{align*}
    \frac{1}{2\pi i}\int_C\frac{1}{\zeta-z}d\zeta=1
  \end{align*}
  なので、結局
  \begin{align*}
    \frac{1}{2\pi i}\int_C\frac{f(\zeta)}{\zeta-z}d\zeta
    =
    f(z)
  \end{align*}
  となる。
{{< /hint >}}

特に上の式から$C$を$z=a$が中心で半径$r$の円周としたとき
\begin{align*}
f(a)=\frac{1}{2\pi}\int^{2\pi}_0f(a+re^{it})dt
\end{align*}
が成り立つ。
つまり、正則関数$f(z)$の$z=a$での値は、その点を中心とする円周上の$f$の値の平均であると理解できる。


{{< hint >}}
  $C=B_2(0)$とする。
  $$
  \int_C\frac{e^z}{z-1}dz= 2\pi ie\\
  \int_C\frac{e^z}{z^2-1}dz=\int_C\frac{e^z}{2}(\frac{1}{z-1}-\frac{1}{z+1})dz
  $$
{{< /hint >}}

## 微分係数の積分表示と正則関数の解析性

コーシーの積分公式を用いることで、正則関数の非常に重要な性質である解析性、
つまり何回でも微分できまた冪級数展開可能であるという性質を導くことができる。

$\phi(\zeta)$は曲線$C$上で連続であるとする。
\begin{align*}
F_1(z)=\int_C\frac{\phi(\zeta)}{\zeta-z}d\zeta
\end{align*}
は$z$について$C$の補集合で連続である。
このことをまず確かめよう。

$z=z_0$での連続性を議論するため、$\delta$を$\abs{z-z_0}&lt;\delta$が$C$と交わらないよう十分小さくとる。
さらに$z$を$\abs{z-z_0}<\dfrac{\delta}{2}$となるよう取ると、
任意の$\zeta\in C$に対し$\abs{\zeta-z}>\dfrac{\delta}{2}$である。

したがって
\begin{align*}
F_1(z)-F_1(z_0)
&=
\int_C\phi(\zeta)(\frac{1}{\zeta-z}-\frac{1}{\zeta-z_0})d\zeta\\
&=
(z-z_0)\int_C\frac{\phi(\zeta)}{(\zeta-z)(\zeta-z_0)}d\zeta
\end{align*}
となる。

これの絶対値を評価すると
\begin{align*}
\abs{F_1(z)-F_1(z_0)}
&\leq
\abs{z-z_0}\int_C\frac{\abs{\phi(\zeta)}}{\abs{\zeta-z}\abs{\zeta-z_0}}\abs{d\zeta}\\
&\leq
\abs{z-z_0}\frac{\delta^2}{2}\int_C\abs{\phi(\zeta)}\abs{d\zeta}
\end{align*}
となる。
この積分は$z, z_0$によらない量であるから、上の不等式から$F_1$の連続性が示される。



次に、$\phi(\zeta)$の代わりに$\dfrac{\phi(\zeta)}{\zeta-z_0}$に対して同様の積分を考えると
\begin{align*}
F_2(z)=\int_C\frac{\phi(\zeta)}{(\zeta-z_0)(\zeta-z)}d\zeta
\end{align*}
も連続である。
つまり、
\begin{align*}
\lim_{z\to z_0}\int_C\frac{\phi(\zeta)}{(\zeta-z_0)(\zeta-z)}d\zeta=F_2(z_0)
\end{align*}
となる。
一方で、この積分は上で見たように
\begin{align*}
\frac{F_1(z)-F_1(z_0)}{z-z_0}=\int_C\frac{\phi(\zeta)}{(\zeta-z)(\zeta-z_0)}d\zeta
\end{align*}
となるから、この左辺の極限は存在し$F_2(z_0)$となる。
この左辺の極限は微分係数の定義で、以上から$F_1'(z_0)=F_2(z_0)$、すなわち
\begin{align*}
f'(z)=\frac{1}{2\pi i}\int_C\frac{f(\zeta)}{(\zeta-z)^2}d\zeta
\end{align*}
が導かれる。



同様に帰納的な議論で
\begin{align*}
F_n(z)=\int_C\frac{\phi(\zeta)}{\zeta-z}d\zeta
\end{align*}
とおくと、これは連続で、
\begin{align*}
F'_n(z)=nF_{n+1}(z)
\end{align*}
を満たす。


{{< hint >}}
  領域$D$で正則な関数$f$に対し、$f$の$n$階導関数は
  \begin{align*}
    f^{(n)}(z)=\frac{n!}{2\pi i}\int_C\frac{f(\zeta)}{(\zeta-z)^{n+1}}d\zeta
  \end{align*}
  を満たす。
  ここで、$C$はその内部まで含めて$D$に含まれる円で、$z$は円の内部の点。
{{< /hint >}}


さらに正則関数はテイラー展開できることもわかる。


{{< hint >}}
  $D, C$に適当な条件をつける。
  $f$は正則とする。このとき、$f$は任意の$n$階微分可能で
  $$
  f^{(n)}(a)=\frac{n!}{2\pi i}\int_C\frac{f(z)}{(z-a)^{n+1}}dz
  $$
  となる。
{{< /hint >}}

{{< hint >}}
  $n$についての数学的帰納法。
  $n=0$の場合はコーシーの積分公式である。

  $n$で成立すると仮定して、$n+1$で示す。
  つまり、$f$は$n$階微分可能であり、
  $$
  f^{(n)}(a)=\frac{n!}{2\pi i}\int_C\frac{f(z)}{(z-a)^{n+1}}dz
  $$
  が成り立つとする。
  この仮定の下で$f^{(n)}$が微分可能であること、そしてその微分係数を計算する。
  $$
  \frac{f^{n}(a+h)-f^{(n)}(a)}{h}=\frac{n!}{2\pi i}\int_C\frac{1}{h}(\frac{1}{(z-(a+h))^{n+1}}-\frac{1}{(z-a)^{n+1}})f(z)dz
  $$
  となる。
  ここで、$A^{n+1}-B^{n+1}=(A-B)(A^n+A^{n-1}B+\cdots+AB^{n-1}+B^n)$であることを用いると、
  $A=\dfrac{1}{z-(a+h)}, B=\dfrac{1}{z-a}$のとき、$A-B=\dfrac{h}{(z-a)(z-(a+h))}$なので、
  $$
  \frac{1}{h}(\frac{1}{(z-(a+h))^{n+1}}-\frac{1}{(z-a)^{n+1}})
  =\frac{1}{(z-a)(z-(a+h))}(\frac{1}{(z-(a+h))^n}+\cdots+\frac{1}{(z-a)^n})
  $$
  となる。
  ここで、$h\to0$とすると、
  $$
  \frac{1}{(z-a)(z-(a+h))}(\frac{1}{(z-(a+h))^n}+\cdots+\frac{1}{(z-a)^n})
  \to\frac{n+1}{(z-a)^{n+2}}
  $$
  となる。
  よって、積分と極限の順序交換をして、
  $$
  \lim_{h\to0}\frac{f^{n}(a+h)-f^{(n)}(a)}{h}=\frac{n!}{2\pi i}\int_C\frac{n+1}{(z-a)^{n+2}}f(z)dz\\
  =\frac{(n+1)!}{d2\pi i}\int_C\frac{f(z)}{(z-a)^{n+2}}dz
  $$
  となる。
  これが証明したいことであった。
{{< /hint >}}

{{< hint >}}
  $$
  \int_{C_i}\frac{1}{z^2(z-1)(z-2)}dz
  $$
  を計算する。
  ここで、$C_1$は$z=0$中心で小さな半径を持つ円、$C_2$は$z=1$中心で小さな半径を持つ円、$C_3$は$z=2$中心で小さな半径を持つ円、
  $C_4$は$z=0,1,2$全てを囲む大きな半径をもつ円である。
  
    $C_1$での積分は、$f(z)=\dfrac{1}{(z-1)(z-2)}$とみて、微分係数の積分表示を使うと
    $$
    \int_{C_1}\frac{f(z)}{z^2}dz=2\pi if'(0)=
    $$
    となる。
  
  
    $C_2$での積分は、$f(z)=\dfrac{1}{z^2(z-2)}$とみて、コーシーの積分公式により
    $$
    \int_{C_2}\frac{f(z)}{z-1}dz=2\pi if(1)=-2\pi i
    $$
    となる。
  
  
    $C_3$での積分は、$f(z)=\dfrac{1}{z^2(z-1)}$とみて、コーシーの積分公式により
    $$
    \int_{C_3}\frac{f(z)}{z-2}dz=2\pi if(2)=\frac{\pi i}{2}
    $$
    となる。
  
  
    $C_4$での積分は、$C_1+C_2+C_3$が$C_4$に$f$がが正則な領域内で連続変形できることから、
    $$
    \int_{C_4}=\int_{C_1}+\int_{C_2}+\int_{C_3}=
    $$
    となる。
  
{{< /hint >}}

## 積分計算への応用


積分定理を使うことで、
初等的には計算の難しい積分を計算できる。


{{< hint >}}
  
    フレネル積分
    \begin{align*}
      \int^\infty_0\cos(x^2)dx=\int^\infty_0\sin(x^2)dx=\frac{\sqrt{\pi}}{2\sqrt{2}}
    \end{align*}
    を計算しよう。
  

  
    曲線$C_R$を原点中心で半径$R$の扇型で弧が偏角が$0$から$\dfrac{\pi}{4}$の部分に反時計回りに向きをつけたものとする。
    この曲線に沿って$f(z)=e^{-z^2}$を積分する。
  

  
    曲線のパラメータづけを
    \begin{align*}
      \gamma_1(t)&=t, t\in[0,R]\
      \gamma_2(t)&=R\exp(i\dfrac{\pi}{4}t), t\in[0,1]\
      \gamma_3(t)&=(R-t)\exp(i\dfrac{\pi}{4}), t\in[0,R]
    \end{align*}
    とする。
  

  
    これらでの積分は
    \begin{align*}
      &\int_0^R\exp(-t^2)dt+\int_0^1\exp(-R^2\exp(i\frac{\pi}{2}t))iR\frac{\pi}{4}\exp(i\frac{\pi}{4}t)dt
      +\int_0^R\exp(-(R-t)^2i)(-\exp(i\frac{\pi}{4}))dt\
    \end{align*}
    となる。
  

  
    第二項は
    \begin{align*}
      \abs{\int_0^1\exp(-R^2\exp(i\frac{\pi}{2}t))iR\frac{\pi}{4}\exp(i\frac{\pi}{4}t)dt}
      &\leq\int_0^1\abs{\exp(-R^2\exp(i\frac{\pi}{2}t))iR\frac{\pi}{4}\exp(i\frac{\pi}{4}t)}dt\\
      &\leq\int_0^1R\exp(-R^2\cos(\frac{\pi}{2}t))\frac{\pi}{4}dt\
    \end{align*}
    となる。
  

  
    さらに、$t\in[0,1]$において$\cos\dfrac{\pi}{2}t\geq1-t$であることから、
    \begin{align*}
      \int_0^1R\exp(-R^2\cos(\frac{\pi}{2}t))\frac{\pi}{4}dt
      &\leq\frac{\pi}{4}R\int_0^1\exp(-R^2(1-t))dt\\
      &=\frac{\pi}{4}R\int_1^0\exp(-R^2s)d(1-s)\\
      &=\frac{\pi}{4}R\int_0^1\exp(-R^2s)ds\\
      &=\frac{\pi}{4}R\frac{-1}{R^2}[\exp(-R^2s)]^1_0
    \end{align*}
    となり、$R\to0$で$0$に収束することがわかる。
  

  
    第一項の計算には
    \begin{align*}
      \int^\infty_{-\infty}\exp(-x^2)dx=\sqrt{\pi}
    \end{align*}
    を用いる。
    第一項について$R\to\infty$での極限は
    \begin{align*}
      \int^\infty_0\exp(-t^2)dt=\frac{\sqrt{\pi}}{2}
    \end{align*}
    となる。
  
  
  
    次に第三項について、
    \begin{align*}
      \int_0^R\exp(-(R-t)^2i)(-\exp(i\frac{\pi}{4}))dt
      &=\int_R^0\exp(-s^2i)(-\exp(i\frac{\pi}{4}))d(R-s)\
      &=-\exp(i\frac{\pi}{4})\int_0^R\exp(-s^2i)ds\
      &=-\exp(i\frac{\pi}{4})\int_0^R\cos(-s^2)+i\sin(-s^2)ds\
    \end{align*}
    となる。
  

  
    $f(z)=\exp(-z^2)$は扇型の内部で正則だから、
    一周積分すると$0$になる。
  

  
    最後に$R\to\infty$の極限をとってをまとめると、
    \begin{align*}
      \frac{\sqrt{\pi}}{2}-\exp(i\frac{\pi}{4})\int_0^\infty\cos(-s^2)+i\sin(-s^2)ds=0
    \end{align*}
    となるので、実部と虚部をそれぞれ比較することで
    \begin{align*}
      \int_0^\infty\cos(-x^2)ds=\int_0^\infty\sin(-x^2)ds=\sqrt{\frac{\pi}{2}}
    \end{align*}
    となる。
  
{{< /hint >}}

{{< hint >}}
  
    \begin{align*}
      \int^\infty_0\frac{\sin x}{x}dx=\frac{\pi}{2}
    \end{align*}
    を証明する。
  

  
    $R, T, \epsilon$をそれぞれ適当な大きさの実数とし、
    $C_1$を$から$R+Ti$を結ぶ線分、$C_2$を+Ti$から$-R+Ti$を結ぶ線分、
    $C_3$を$-R+Ti$から$-R$を結ぶ線分、$C_4$を$-R$から$-\epsilon$を結ぶ線分、
    $C_5$を原点中心で半径$\epsilon$の上半円周を時計回りに向きをつけたもの、
    $C_6$を$\epsilon$から$R$を結ぶ線分とする。
  

  
    この曲線に沿って$f(z)=\dfrac{e^{iz}}{z}$を積分する。
    上の曲線で囲まれた領域の内部で$f(z)$は正則だから、一周積分した値は$0$である。
  

  
    まず$C_1$ではパラメータを$R+ti$とつけることで、
    \begin{align*}
      \abs{\int_0^T\frac{\exp(iR-t)}{R+ti}idt}
      &\leq\int_0^T\abs{\frac{\exp(iR-t)}{R+ti}}dt\
      &\leq\int_0^T\frac{\exp(-t)}{R}dt\
      &\leq\int_0^\infty\frac{\exp(-t)}{R}dt\
      &\leq\frac{1}{R}
    \end{align*}
    となり、これは任意の$T$について$R\to\infty$で$0$に収束する。
    $C_3$についても同様。
  

  
    $C_2$ではパラメータを$t+Ti$とつけることで
    \begin{align*}
      \abs{\int_R^{-R}\frac{\exp(it-T)}{t+Ti}dt}
      &\leq\frac{1}{T}\int^{-R}_R\exp(-T)dt\
      &=\frac{2Re^{-T}}{T}
    \end{align*}
    となり、これは任意の$R$について$T\to\infty$で$0$に収束する。
  

  
    $C_4, C_6$での積分については
    \begin{align*}
      \int_{-R}^{-\epsilon}\frac{\exp(iz)}{z}dz
      +\int_\epsilon^R\frac{\exp(iz)}{z}dz
      &=
      \int_\epsilon^R\frac{\exp(-iz)}{-z}dz
      +\int_\epsilon^R\frac{\exp(iz)}{z}dz\
      &=
      2i\int^R_\epsilon\frac{\sin z}{z}dz
    \end{align*}
    となる。
    $\epsilon\to0, R\to\infty$の極限を取ることで求めるべき積分値に収束する。
  

  
    最後に$C_5$での積分について見てみよう。
    $\exp(iz)$は全複素平面で正則函数であり、$z=0$の周りのテイラー展開を考えることで
    \begin{align*}
      \frac{\exp(iz)}{z}=z^{-1}+g(z)
    \end{align*}
    と収束半径$\infty$の冪級数$g(z)$を用いて表すことができ、
    この$g(z)$は$\abs{z}\leq1$に対し$\abs{g(z)}\leq M$なる$M$が存在する。
    このことにより、
    \begin{align*}
      \abs{\int_{C_5}g(z)dz}\leq\pi\epsilon M
    \end{align*}
    となり、$\epsilon\to0$で$0$に収束する。
    一方、直接計算により
    \begin{align*}
      \int_{C_5}z^{-1}dz=-\pi i
    \end{align*}
    となるから、$\epsilon\to0$の極限で
    \begin{align*}
      \int_{C_5}\frac{\exp(iz)}{z}dz\to-\pi i
    \end{align*}
    である。
  

  
    これらを全てまとめ、$T\to\infty, R\to\infty, \epsilon\to0$の順に極限を取ることで
    \begin{align*}
      2i\int^\infty_0\frac{\sin x}{x}dx-\pi i=0
    \end{align*}
    が得られる。
  
{{< /hint >}}

{{< hint >}}
  \begin{align*}
    \frac{1}{\sqrt{2\pi}}\int^\infty_{-\infty}\exp(-x^2-itx)dx
  \end{align*}
  を計算しよう。

  $z=b, b+\dfrac{it}{2}, -a+\dfrac{it}{2}, -a$を頂点にもつ長方形の周に反時計回りに向きをつけた曲線を$C$とする。
  このとき、虚軸と平行な辺での積分は
  \begin{align*}
    \abs{\int^{b+it/2}_bf(z)dz}
    &\leq e^{-b^2}\int_0^{t/2} e^{y^2}dy\\
    &\leq \frac{t}{2}e^{-b^2}e^{t^2/4}
  \end{align*}
  となり、これは$b\to\infty$で$0$に収束する。
  もう一つの辺についても同様。

  したがって、$C$での積分が$0$であることから、さらに$a,b\to\infty$での極限を考えると、
  長方形の残りの辺での積分値は一致する。

  よって
  \begin{align*}
    \frac{1}{\sqrt{2\pi}}\int^\infty_{-\infty}\exp(-x^2-itx)dx
    &=
    \frac{e^{-t^2/4}}{\sqrt{2\pi}}\int^\infty_{-\infty}\exp(-(x+it/2)^2)dx\\
    &=
    \frac{e^{-t^2/4}}{\sqrt{2\pi}}\int^\infty_{-\infty}\exp(-x^2)dx\\
    &=
    \frac{1}{\sqrt{2}}e^{-t^2/4}
  \end{align*}
  と計算できる。
{{< /hint >}}
