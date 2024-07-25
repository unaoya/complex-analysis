---
title: "留数定理"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# 留数定理

## 留数とは

次に留数という概念について見ていこう。
まず思い出して欲しいのは、次の積分計算である。
$C$を反時計回りの単位円周とする。
$$
  \int_C\frac{dz}{z}=2\pi i
$$
コーシーの積分定理から、上の$C$は単位円周でなくても同じ式が成り立つ。
単位円周であるという条件は具体的に計算を行うための条件である。
  
この計算を念頭において、次のように留数を定義する。
  
{{< hint >}}
  孤立特異点$z=a$での$f(z)$の留数とは、ある円環$0<\lvert z-a\rvert<\delta$で
  $$
    f(z)-\frac{R}{z-a}
  $$
  が$1$価正則関数の導関数になるような複素数$R$のことである。

  これを$R=Res_{z=a}f(z)$と表す。
{{< /hint >}}

{{< hint >}}
  $f(z)=\dfrac{C}{z-a}$について、$C$が$z=a$における留数である。
{{< /hint >}}

{{< hint >}}
  $z=a$が極の場合、その留数はローラン展開の$-1$次の係数と一致する。
{{< /hint >}}


留数とは。
正則関数$f$の$z=\alpha$を中心とするローラン展開
$$
  f(z)=\sum_{n=-\infty}^\infty a_n(z-\alpha)^n
$$
において、径数$a_n$は
$$
  a_n=\frac{1}{2\pi i}\int_{\lvert\zeta-\alpha\rvert=r}\frac{f(\zeta)}{(\zeta-\alpha)^{n+1}}d\zeta
$$
と表すことができた。
このうち、$(z-\alpha)^{-1}$の係数$a_{-1}$を$z=\alpha$における留数といい、
$$
  a_{-1}=Res_{z=\alpha}f(z)
$$
と表す。

つまり、
$$
  Res_{z=\alpha}f(z)=\frac{1}{2\pi i}\int_{\lvert\zeta-\alpha\rvert=r}f(z)dz
$$
である。

いくつか簡単な例を見ていこう。
  
留数の求め方。
$\alpha$が$n$位の極のとき、
$$
  Res_{z=\alpha}f(z)=\frac{1}{(n-1)!}\lim_{z\to\alpha}\frac{d^{n-1}}{dz^{n-1}}f(z)
$$
である。
特に$n=1$なら
$$
  Res_{z=\alpha}f(z)=\lim_{z\to\alpha}(z-\alpha)f(z)
$$
である。
  

{{< hint >}}
  $f(z)=\dfrac{z-2}{z^2(z-1)^3}$の極を全て求め、その留数を求めよ。
{{< /hint >}}

## 留数定理

{{< hint >}}
  単純閉曲線$C$で囲まれる領域を$D$とする。
  関数$f$は$\alpha_1,\ldots,\alpha_k\in D$をのぞき$\overline{D}$で正則であるとする。
  このとき、
  $$
    \int_Cf(z)dz=2\pi i\sum_{j=1}^k Res_{z=\alpha_j}f(z)
  $$
  が成り立つ。
{{< /hint >}}

{{< hint >}}
  証明を書く。
{{< /hint >}}
  
{{< hint >}}
  $$
    \int_{B_1(i)}\frac{1}{z^2+1}dz\\
    \int_{B_2(0)}\frac{z^2}{(z+1)^3}dz\\
    \int_{B_2(0)}\frac{\sin z}{z(z^2+1)}dz
  $$
{{< /hint >}}
  
{{< hint >}}
  領域$D$において、$f$は有限個の孤立特異点$a_1,\ldots,a_n$をのぞいて正則であるとする。
  $D$内のサイクル$C$が$0$にホモローグで、どの$a_i$も通らないとする。
  このとき、
  $$
    \frac{1}{2\pi i}\int_Cf(z)dz=\sum_in(C,a_i)Res_{z=a_i}f(z)
  $$
  が成り立つ。
{{< /hint >}}

{{< hint >}}
  $$
    \int^\infty_{-\infty}\frac{1}{x^2+1}dx
  $$
  を計算せよ。
  ちなみに、これは積分定理を用いずとも計算可能で、$x=\tan\theta$と置き換えることにより積分の値は$\pi$と求めることができる。

  積分経路$C_R$を半径$R$で原点中心の円の上半分と実軸の$-R$から$R$を結ぶ線分を合わせてできる半円の境界に反時計回りの向きをつけたものとする。

  このとき、
  $$
    f(z)=\frac{1}{z^2+1}=\frac{1}{2i}(\frac{1}{z-i}-\frac{1}{z+i})
  $$
  は$z=i$で$1$位の極をもち、そこでの留数は$\dfrac{1}{2i}$である。
  また、それ以外では正則である。

  したがって、留数定理より
  $$
    \frac{1}{2\pi i}\int_{C_R}\frac{1}{x^2+1}dx=\frac{1}{2i}
  $$
  となる。

  $C_R$の円弧の部分$C_R$の積分は次のようにして$R\to\infty$での値を評価できる。
  まず、$\lvert z\rvert=R$であれば
  $$
    \lvert \frac{1}{z^2+1}\rvert\leq\lvert\frac{1}{R^2+1}\rvert
  $$
  である。
  したがって、
  $$
    \lvert\int_{C_R}\frac{1}{z^2+1}dz\rvert
    =
    \lvert\int^\pi_{0}\frac{1}{R^2\exp(2\pi it)+1}R2\pi i\exp(2\pi it)dt\rvert
    \leq
    2\pi R\int^\pi_{0}\frac{1}{R^2+1}dt
    =
    2\pi^2\frac{R}{R^2+1}
  $$
  となるので、$R\to\infty$でこの積分は$0$に収束することがわかる。

  以上から、$R\to\infty$での極限を考えることで
  $$
    \int_{-\infty}^\infty\frac{1}{x^2+1}dx=\pi
  $$
  となる。
{{< /hint >}}

## 偏角の原理

有理形関数$f(z)$を$z=a$の周りでローラン級数展開することで、$f\'(z)/f(Z)$の$z=a$での留数が$f(z)$の$z=a$での極や零点の位数を用いて計算できることがわかる。
このことを使うと以下がわかる。    

{{< hint >}}
  $f(z)$は$\Omega$で有理形で、その零点を$a_1,\ldots,a_n$、極を$b_1,\ldots,b_m$とする。
  $\Omega$に関して$0$にホモローグで零点も極も通らない任意のサイクル$C$に対し
  $$
    \frac{1}{2\pi i}\int_C\frac{f\'(z)}{f(z)}dz=\sum_{i=1}^nn(C,a_i)-\sum_{j=1}^mn(C,b_j)
  $$
  となる。  
{{< /hint >}}

$f$による$C$の像を$\Gamma$とし、$w=f(z)$とすると
$$
  \frac{1}{2\pi i}\int_C\frac{f\'(z)}{f(z)}dz=\frac{1}{2\pi i}\int_\Gamma\frac{dw}{w}=n(\Gamma,0)
$$
となる。
このことから、この積分は$f(z)$の偏角の増加量と解釈できる。    

さらに次のように一般化できる。
$g(z)$を$\Omega$で正則とすると、$g(z)\dfrac{f\'(z)}{f(z)}$は$f$の$h$位の零点$z=a$では留数$hg(a)$をもち、
$f$の$h$位の極では留数$-hg(a)$を持つ。
よって
$$
  \frac{1}{2\pi i}\int_Cg(z)\frac{f\'(z)}{f(z)}dz=\sum_{i=1}^nn(C,a_i)g(a_i)-\sum_{j=1}^mn(C,b_j)g(b_j)
$$
が成り立つ。