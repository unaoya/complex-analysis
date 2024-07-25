---
title: "Holomorphic Function"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---
<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="utf-8"/>
<link rel="stylesheet" href="../style.css">
<script type="text/javascript" src="../config.js" defer></script>
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-AMS_CHTML"></script>
<title>第3回</title>
</head>
<body>
<h1>第3回</h1>

    正則関数．初等関数(1)
    正則関数を定義し，正則性の判定に使われるコーシー・リーマンの方程式を解説する．
    その後で正則関数の例として，多項式関数・有理関数，指数関数，三角関数について解説する．


## 複素関数

    複素関数。
    $f:\CC\to \CC$とか、$U\subset\CC$に対して$f:U\to\CC$を考える。



    複素関数の連続性。
    複素関数の連続性は、単に二変数関数$f(x,y)$の連続性と同じ。
    $\CC$の位相は$\RR^2$の位相と同じで、距離を絶対値で測る。
    $z=x+iy, w=u+vi$としたとき、$z, w$の距離と$(x,y), (u,v)$の距離は同じ。
    連続であることは
    $$
    \lim_{z\to a}f(z)=f(a)
    $$
    で定義する。
    $\epsilon\delta$でかくと、任意の$\epsilon>0$に対し、ある$\delta$が存在して、
    $\lvert z-a\rvert&lt;\delta$ならば$\lvert f(z)-f(a)\rvert&lt;\epsilon$である。



    複素関数の微分。
    $$
    \lim_{z\to a}\frac{f(z)-f(a)}{z-a}
    $$
    が存在するとき、$f$は$a$で複素微分可能といい、極限値を$f'(a)$と表す。
    二変数関数の偏微分や全微分との比較。
    単に一次関数で近似できるのみではなく、複素一次関数で近似できるということ。
    これが全然違う。
    等角性、調和関数



  一次関数は$f(z)=\alpha z+\beta$で、
  これは$\alpha$倍で回転拡大、$+\beta$で平行移動を表す。
  図示する。



  $\CC$を$\RR^2$とみなすことで、複素関数$f:\CC\to \CC$は実二変数のベクトル値関数$f:\RR^2\to\RR^2$とみなすことができる。
  さらに、距離の対応もつくため、関数の連続性はどちらで見ても同値である。
  しかし、大きな違いが関数の美文についてである。
  あるいはどのように一次近似をするかが異なる。


## 正則関数の定義

    まずは正則関数の定義を確認しよう。


{{< hint >}}
    開集合$D\subset \CC$を定義域にもつ関数$f:D\to\CC$が正則であるとは、
    任意の$z\in D$について以下の極限が存在すること。
    \begin{align*}
      f'(z)=\lim_{h\to0}\frac{f(z+h)-f(z)}{h}
    \end{align*}
  
    ここで右辺の極限は複素数の範囲で任意の$h\to 0$の近付け方について同じ値に収束することを条件としている。  
{{< /hint >}}


  これは開集合$U\subset\RR$を定義域にもつ関数の$f:\RR\to \RR$の微分係数の定義
  \begin{align*}
    f'(a)=\lim_{h\to0}\frac{f(a+h)-f(a)}{h}
  \end{align*}
  と式の形は同じである。
  ただし、$h\to0$の近付け方が$\RR$の開集合の場合は本質的に二つしかないのに対し、$\CC$の開集合の場合は様々ある点が異なる。



  実数関数において、微分係数は一次式による近似の比例定数を表していた。
  つまり、上の微分係数の定義式は
  \begin{align*}
    \lim_{h\to0}\frac{f(a+h)-f(a)-f'(a)h}{h}=0
  \end{align*}
  と同値である。
  これは、
  \begin{align*}
    f(a+h)=f(a)+f'(a)h+o(h)
  \end{align*}
  という$h$についての一次式の近似を表していると解釈できる。
  ここで、$f(a)+f'(a)h$は$h$についての実数係数の$1$次式である。



  これと同様に考えると、$f:\CC\to\CC$の微分可能性は複素係数の$1$次式$f(a)+f'(a)h$による近似可能性ということができる。



  また$2$変数関数$f:\RR^2\to\RR^2$の微分可能性とも比較しよう。
  こちらは成分が実数の$2$次正方行列$A$により
  \begin{align*}
    \lim_{(h,k)\to0}\frac{f(a+h)-f(a)-A{}^t(h,k)}{\abs{(h,k)}}=0
  \end{align*}
  となることであった。
  こちらは複素関数の微分係数の定義と同様に、全ての近づき方を考える。



  一方で複素数$a+bi$倍を$1,i$を基底として行列で表すと$\begin{pmatrix}a&-b\\b&a\end{pmatrix}$の形になる。
  つまり、近似する行列の形に制約があるのが複素関数の微分の定義であると考えることができる。
  このように、単に$z=x+iy$と表示した上での$2$変数関数としての微分可能性に比べて、
  複素関数としての微分可能性の方が真に強い条件であることがわかる。



  それでは正則関数の例について見ていこう。


{{< hint >}}
  $f(z)=z^2$は$z=\alpha$の周りで一次式$2\alpha(z-\alpha)+\alpha^2$で近似できる。
  これを図示して確かめよう。
  $f(z)=z^2$で実軸平行な直線や虚軸平行な直線がどのように映るかを書いてみる。
{{< /hint >}}

{{< hint >}}
  $n$を$0$以上の整数として$f(z)=z^n$は正則関数である。
{{< /hint >}}

{{< hint >}}
  正則関数どうしの和や積は正則関数である。
{{< /hint >}}

{{< hint >}}
  $z$についての多項式は正則関数である。
{{< /hint >}}

{{< hint >}}
  $z$についての有理式は、分母が$0$になる点を除いて正則関数である。
{{< /hint >}}


  それでは正則でない関数にはどのようなものがあるか。


{{< hint >}}
  $f(z)=\bar{z}$は正則ではない。

  まず直感的な説明をする。
  $f(z)=az+b$と近似できるのであれば、実軸と虚軸の角は保たれる。
  ところが、$f(z)$でうつすと実軸と虚軸の向きが逆になる。
  よって、一次式で近似することはできない。

  また、これは等角ではないため正則ではないということもできる。
  複素係数の一次式で近似できるなら、近似的には等角である。
  回転拡大と平行移動は等角なため。

  また、$f(z)=x-iy$を二変数関数と見たとき、$A=\begin{pmatrix}1&0\\0&-1\end{pmatrix}$が$f(z)$を近似する（この場合には近似ではなくて一致するが）行列となる。

  定義に直接基づいた証明も行おう。
  $h$が実数で近づいた場合と、純虚数で近づいた場合に極限値が異なることを確かめる。
  $z=x+iy$として
  \begin{align*}
    \lim_{h\to0, h\in\RR}\frac{(x+h-iy)-(x-iy)}{h}&=1\\
    \lim_{h\to0, h\in\RR}\frac{(x-i(y+h))-(x-iy)}{ih}&=-1\\
  \end{align*}
  となるので、微分可能でない。
{{< /hint >}}

{{< hint >}}
  $f(z)=\abs{z}$は正則ではないことを示せ。
{{< /hint >}}


  上で述べたように、正則関数は一次式で近似できる関数と見ることができる。
  $f$が$z=z_0$で正則であり$f'(z_0)\neq0$とする。
  $z_0$を通る二曲線について$z_0$での接線を$f$でうつして得られる$f(z_0)$を通る二曲線の接線を考える。
  このとき、うつす前の接線のなす角とうつした後の接線のなす角は一致する。



  というのも、$z(t)$を曲線$C$のパラメータとし、$w(t)=f(z(t))$を$で$をうつした曲線のパラメータとすると、
  $w'(t)=z'(t)f'(z(t))$より
  \begin{align*}
    \arg{w'(t)}=\arg{(z'(t)}+\arg{f'(z(t))}
  \end{align*}
  となるためである。
  この性質を等角性という。



    正則関数。
    $\CC$内の領域$U\subset\CC$の各点で複素微分可能。



    単に$1$点で複素微分可能であることと違うのか。
    実関数の場合は？



    コーシーリーマンの方程式
    $u_x=v_y, u_y=-v_x$のこと。
    
    $\partial_z, \partial_{\bar{z}}$で書くこともできる。・
    
    正則関数を$\mathbb{R}^2\to\mathbb{R}^2$と見た時のヤコビ行列。
    $f(z)=u(x,y)+iv(x,y)$とおくと、$\begin{pmatrix}u_x&v_x\\u_y&v_y\end{pmatrix}$であり、
    $\begin{pmatrix}a&-b\\b&a\end{pmatrix}$の形。
    
    $\begin{pmatrix}0&-1\\1&0\end{pmatrix}$との交換？
    複素構造。
    
    線型写像が角を保つ条件は？
    
    複素一次関数による近似。
    
    調和関数との関係。



    正則関数の等角性
    $z_0$で交わる適切な滑らかさの曲線$\gamma_1, \gamma_2$について、
    $z_0$での接ベクトルのなす角と、
    $f(z_0)$において$f(\gamma_1), f(\gamma_2)$の接ベクトルのなす角の大きさは等しい。
    写像の微分により、ヤコビアンで解釈できる。


## 正則関数の例


    正則関数の和や積、逆数もまた正則関数である。



    多項式関数。
    $z$の多項式で定まる関数$f(z)=z^n+\cdots+a_n$は正則関数である。
    これは$\CC$全体で定義された正則関数である。



    有理関数。
    多項式函数の比で定まる関数を有理関数という。
    これは$\CC$から分母が$0$になる点を除いて正則関数になる。



    指数関数。
    $\exp z$は正則関数である。
    そもそも複素関数としての$\exp z$はどう定義されるか。
    オイラーの公式を用いて定義するのが一つのやり方。


{{< hint >}}
  $z\in\CC$を$z=x+yi$と表したとき、
  \begin{align*}
    \exp(z)=e^x(\cos y+i\sin y)
  \end{align*}
  と定める。
{{< /hint >}}


    三角関数。
    複素関数としての$\sin z, \cos z$はどう定義されるか。




上の定義において、$e^r, \cos\theta, \sin\theta$はいずれも実数を定義域にもつ関数としての指数関数や三角関数であることに注意しよう。

指数関数の様子を把握するために、$x$一定の曲線や$y$一定の曲線がどのようにうつるかをみておこう。

次のような冪級数を定義とする方法もある。
\begin{align*}
  \exp(z)=1+z+\frac{1}{2}z^2+\frac{1}{3!}z^3+\cdots
\end{align*}

この二つの定義の同値性は証明が必要だが、今回は省略する。

{{< hint >}}[一次分数変換]
  $f(z)=\dfrac{az+b}{cz+d}$を一次分数変換という。
  これは$\CC\setminus\{\dfrac{-d}{c}\}$で正則な関数である。

  $\CC$に無限遠点$\{\infty\}$を付け加えてリーマン球面を考える。
  すると、一次分数変換はリーマン球面からリーマン球面への「正則関数」となる。
  この関数により、リーマン球面の「円」は「円」にうつる。

  リーマン球面における「円」は通常の複素平面における円または直線である。
{{< /hint >}}

## コーシーリーマン方程式

  複素関数の微分係数を調べるとき、$h\to 0$の全ての近付け方について極限
  \begin{align*}
    \lim_{h\to0}\frac{f(a+h)-f(a)}{h}
  \end{align*}
  が一定であった。



  実部と虚部を$f(z)=u(z)+iv(z)$と表すことにし、
  さらに必要に応じて$z=x+yi$として$f(x,y), u(x,y), v(x,y)$のように考える。
  $h$を実数で近づけると
  \begin{align*}
    f'(z)=\frac{\partial u}{\partial x}(z)+i\frac{\partial v}{\partial x}(z)
  \end{align*}
  である。
  $$
    \lim_{h\to0}\frac{f(z+h)-f(z)}{h}=\lim_{h\to0}\frac{f(x+h,y)-f(x,y)}{h}\\
    =\lim_{h\to0}(\frac{u(x+h,y)-u(x,y)}{h}+\frac{iv(x+h,y)-iv(x,y)}{h})
  $$
  であり、それぞれの極限が存在すること（例えば絶対値評価）から、
  $$
    =\lim_{h\to0}\frac{u(x+h,y)-u(x,y)}{h}+i\lim_{h\to0}\frac{v(x+h,y)-v(x,y)}{h}\\
    =\frac{\partial u}{\partial x}+i\frac{\partial v}{\partial x}
  $$
  一方で、$h=ik$を純虚数で近づけると
  \begin{align*}
    f'(z)&=\lim_{ik\to0}\frac{f(x,y+k)-f(x,y)}{ik}\\
    &=-i\frac{\partial u}{\partial y}(z)+\frac{\partial v}{\partial y}(z)
  \end{align*}
  となる。
  上と同様の議論で、$h=ik$として
  $$
    \lim_{h\to0}\frac{f(z+h)-f(z)}{h}=\lim_{k\to0}\frac{f(x,y+k)-f(x,y)}{ik}\\
    =\lim_{k\to0}(\frac{u(x,y+k)-u(x,y)}{ik}+\frac{iv(x,y+k)-iv(x,y)}{ik})\\
    =\lim_{k\to0}\frac{u(x,y+k)-u(x,y)}{ik}+i\lim_{k\to0}\frac{v(x,y+k)-v(x,y)}{ik}\\
    =-i\frac{\partial u}{\partial x}+\frac{\partial v}{\partial x}
  $$



  この二つが一致するので、
  \begin{align*}
    \frac{\partial u}{\partial x}&=\frac{\partial v}{\partial y}\\
    -\frac{\partial u}{\partial y}&=\frac{\partial v}{\partial x}
  \end{align*}
  となる。
  これをコーシーリーマン方程式という。



  先ほどのいくつかの実例についてコーシーリーマン方程式を確かめよう。


{{< hint >}}
  $f(z)=z$に対し、実部は$u(x,y)=x$であり、虚部は$v(x,y)=y$である。
  \begin{align*}
    \frac{\partial u}{\partial x}&=\frac{\partial v}{\partial y}=1\\
    -\frac{\partial u}{\partial y}&=\frac{\partial v}{\partial x}=0\\
  \end{align*}
  となり、コーシーリーマン方程式が成立する。

  $f(z)=z^2, z^3$などについても直接確かめよ。
{{< /hint >}}

{{< hint >}}
  $f(z)=\bar{z}$に対し、実部は$u(x,y)=x$であり、虚部は$v(x,y)=-y$である。
  \begin{align*}
    \frac{\partial u}{\partial x}&=1\\
    \frac{\partial v}{\partial y}&=-1\\
  \end{align*}
  なので、コーシーリーマン方程式は成立しない。
{{< /hint >}}


  さらに$u, v$がさらに偏微分可能であることを仮定すると、（実際にはあとで見るように$f$が複素で微分可能なら常に成立する条件である。）この式から
  \begin{align*}
    \frac{\partial^2 u}{\partial x^2}&=\frac{\partial^2 v}{\partial x\partial y}\
    -\frac{\partial^2 u}{\partial y^2}&=\frac{\partial^2 v}{\partial x\partial y}\
  \end{align*}
  となるので、
  \begin{align*}
    \frac{\partial^2 u}{\partial x^2}+\frac{\partial^2 u}{\partial y^2}&=0
  \end{align*}
  となる。
  $v$についても同様で、$u, v$は調和関数であることがわかる。
  さらにこの$u, v$は無関係な二つの関数というわけではなく、コーシーリーマン方程式を満たす調和関数の組である。
  このようなものを共役調和関数という。


{{< hint >}}
  $u(x,y)=x^2+y^2$のような関数は正則関数の実部や虚部となることはない。
{{< /hint >}}


  逆に$u(x,y), v(x,y)$が偏微分可能かつ偏導関数が連続で、コーシーリーマン方程式を満たすとき、
  $f(z)=u(x,y)+iv(x,y)$は正則関数で$f'(z)$は連続となる。



  また、調和関数$u(x,y)$が与えられたとき、それを実部（または虚部）にもつ正則関数を構成することができる。


{{< hint >}}
  $u(x,y)=x^2-y^2$とする。
  これは調和関数であり、共役調和関数$v(x,y)$は
  \begin{align*}
    \frac{\partial v}{\partial x}&=2y\\
    \frac{\partial v}{\partial y}&=2x\\
  \end{align*}
  の解である。

  一つ目の式から$v(x,y)=2yx+g(y)$となり、さらに二つ目の式から$g(y)=c$となる。
  よって、$v(x,y)=2xy+c$とすればよく、
  \begin{align*}
    f(x+yi)=(x^2-y^2)+i(2xy+c)
  \end{align*}
  は正則関数である。
{{< /hint >}}


  つまり、正則関数が存在するかどうかは調和関数が存在するかどうかで判断でき、
  \begin{align*}
    \Delta u=0
  \end{align*}
  の解を求めることになる。



  関数が正則ならコーシーリーマン方程式を満たす。
  逆はどうか？
  例えば$u, v$が全微分可能であるとき、あるいは$C^1$級であるときは言える。
  また、そのとき$f'(z)= u_x+iv_x$が成立する。



  コーシーリーマン方程式は、$f$の微分係数の制約と思うことができる。
  実二変数関数と思って近似した時の行列$A$が$a=d, b=-c$となるという条件。
  また、これは$\begin{pmatrix}1&0\\0&1\end{pmatrix}$と交換するという条件と同値である。
  また、複素数を複素数倍として$\CC$に定まる線形写像の基底$1,i$による行列表示により定まる$\CC\to M_2(\RR)$の像である。



  コーシーリーマン方程式は、ベクトル$\begin{pmatrix}u_x\\v_x\end{pmatrix}$と$\begin{pmatrix}u_y\\v_y\end{pmatrix}$のなす角が$90^\circ$という条件である。
  これが一般の曲線についても成り立つというのが等角性。



  正則関数の等角性



  $\dfrac{\partial}{\partial z}=\frac{1}{2}(\frac{\partial}{\partial x}+i\frac{\partial}{\partial y})$とおき、
  $\dfrac{\partial}{\partial \bar{z}}=\frac{1}{2}(\frac{\partial}{\partial x}-i\frac{\partial}{\partial y})$とおく。
  コーシーリーマン方程式は$\dfrac{\partial}{\partial \bar{z}}f=0$と同値。
  接空間を複素化してその実ベクトル空間としての取り替えたもの。


## 初等関数


  多項式と有理式。
  正則関数の和や積は正則、商は分母が$0$でない範囲で正則。



  指数関数。$e^z, \exp(z)$をどう定義するか。
  いくつかのやり方がある。
  冪級数、オイラーの公式、微分方程式など。
  等角な拡張として特徴づけられる。
  例えば、天下りに$f(z)=e^{x+iy}=e^x(\cos y+i\sin y)$と定義してみる。
  （ここでは実数の範囲での指数関数と三角関数しか用いていないことに注意する。）
  すると、これについて$u, v$は全微分可能であり、コーシーリーマン方程式を満たすことも直接計算できる。
  さらに導関数は$f'(z)=f(z)$となることもわかる。
  上で与えた天下りな式は、指数法則の等角性から導出することもできる。
  この関数について、周期$2\pi i$をもつ。
  特に単車ではないため、全域で逆関数を持たない。



  三角関数を定義する。
  上の指数関数の定義において、$\theta$を実数として、$e^{i\theta}=\cos\theta+i\sin\theta$となることから、
  $$
  \dfrac{e^{i\theta}+e^{-i\theta}}{2}=\cos\theta\\
  \dfrac{e^{i\theta}-e^{-i\theta}}{2}=\sin\theta
  $$
  が成り立つ。
  これをそのまま複素数に拡張する。
  $$
  \cos
  $$
  すると、これはコーシーリーマン方程式を満たし実部虚部が全微分可能なので、正則関数となることがわかる。

  また、$(\cos z)'=-\sin z, (\sin z)'=\cos z$であり、
  加法定理が成り立つことも証明できる。



  ちなみに、後ほど証明する正則関数の一致の定理によれば、
  二つの関数$f(z), g(z)$が$z\in\RR$で一致するならば$f=g$であることが証明できる。
  したがって、拡張が正則になればそれが唯一の正則な拡張であることが保証される。



  対数関数をどう定義するか。
  実数の範囲では、指数関数の逆関数として定義できた。
  複素数の範囲では、指数関数が複数の複素数で同じ値をとる。
  なので、逆関数が直ちには定義できない。



次に対数関数の定義を考えよう。
対数関数は指数関数の逆関数として定義する。
指数関数は
\begin{align*}
  \exp(z)=e^x(\cos y+i\sin y)
\end{align*}
であった。
$\cos, \sin$が周期$2\pi$の周期関数であることを思い出す。



  $w=u+vi=e^z$として、$x, y$について解く。
  $w$の絶対値が$e^x$であり、偏角が$y$である。
  したがって、$x=\log\lvert w\rvert$であり、$y=\arg w$である。



そこで、$z=r(\cos\theta+i\sin\theta)$であるときに
\begin{align*}
  \log(z)=\log r+i\theta
\end{align*}
とする。
つまり、
$$
\log(z)=\log\lvert z\rvert+i\arg z
$$
である。
ただし、偏角$\theta$は一意には定まらないことに注意しよう。



例えば$z=1$で$\theta=0$と選んだとき、
単位円周を反時計回りに一周動いて$\log z$の値の変化をみてみる。
このとき$r=1$で一定で、$\theta$が連続的に増加させると、$1$周回って$z=1$に戻ったときに$\theta=2\pi$になる。
つまり、$\CC$上で一価正則関数として$\log z$を定義できないということになる。
これは$z=0$の周りを回ることによって不定性が生じるからである。



あとで複素線積分やコーシーの積分定理などについてみると
\begin{align*}
  \log z=\int^z_1\frac{1}{t}dt
\end{align*}
という積分の値が経路によって変化するという現象に対応していることがわかる。



  冪函数。
  一般の複素数$a$に対して$a^z$を以下にして定義するか。
  対数関数を用いる。
  多価関数になる。



べき関数の定義を与えよう。
例えば$f(z)=\sqrt{z}$でも上の対数関数と同様に$\CC$上で一価正則な関数として定義することはできない。
単位円周に沿って一周連続的に$\sqrt{z}$の値を変化させるとどうなるかを考えよう。



一般の$\alpha$に対し、
\begin{align*}
  z^\alpha=\exp(\alpha\log z)
\end{align*}
と定義する。
これは多価関数となることに注意せよ。
$\alpha\log z$の不定性を$\exp$が消す場合がある。
$\alpha$が整数であれば一価正則に定まる。
有理数であれば有限通りの不定性がある。


</body>
</html>