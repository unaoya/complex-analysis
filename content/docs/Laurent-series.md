---
title: "ローラン級数展開"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# ローラン級数展開

ローラン級数展開について。
正則関数は冪級数展開可能であった。
孤立特異点の周りでローラン級数展開可能であることを確かめる。
孤立特異点におけるローラン展開，極と真性特異点について解説する．

## 孤立特異点

複素関数$f$が$z=\alpha$の周りで$\alpha$を除いて定義されかつ正則、
つまりある正の数$R$が存在して$0 &lt; \abs{z-\alpha} &lt; R$上で$f$が正則なとき、
$\alpha$を$f$の孤立特異点という。

{{< hint >}}

    $f(z)$が$z=a$の近傍で$z=a$を除いて正則であるとする。
    つまり、ある$\delta$について$0&lt;\abs{z-a}&lt;\delta$で$f(z)$が正則であるとする。
  
    このとき、$z=a$を$f(z)$の孤立特異点という。
{{< /hint >}}

孤立特異点の例を見ていく。

{{< hint >}}
  $f(z)=\dfrac{1}{z}, f(z)=\dfrac{1}{\sin z}$
{{< /hint >}}

{{< hint >}}
  $f(z)=\log z$の$z=0$は孤立特異点ではない。
{{< /hint >}}

{{< hint >}}
  $f(z)$が正則な点も孤立特異点である。
{{< /hint >}}

## ローラン級数展開

$z=a$を$f(z)$の孤立特異点としよう。
このとき、$f$は$z=a$の周りでローラン展開
$$
    f(z)=\sum_{n=-\infty}^\infty a_n(z-a)^n
$$
を持つ。
ローラン級数展開の係数$a_n$は積分表示を持つ。

特に負冪部分
$$
    \sum_{n=-\infty}^{-1} a_n(z-a)^n
$$
を主要部という。

$f$が$z=\alpha$を孤立特異点に持つとする。
$\alpha$を中心とする同心円$C_1, C_2$を考え、半径の小さい方を$C_1$とする。
$C_1, C_2$に挟まれた部分にある点$z$をとる。
円の向きはいずれも反時計回り。
$z$を中心とする小さな円を$C$とすると、コーシーの積分定理より
$$
f(z)=\frac{1}{2\pi i}\int_C\frac{f(\zeta)}{\zeta-z}d\zeta
$$
であり、一方で$f$の正則性から積分路を連続変形して$\int_C=-\int_{C_1}+\int_{C_2}$であるから、
$$
f(z)=-\frac{1}{2\pi i}\int_{C_1}\frac{f(\zeta)}{\zeta-z}d\zeta+\frac{1}{2\pi i}\int_{C_2}\frac{f(\zeta)}{\zeta-z}d\zeta
$$
となる。

$$
\dfrac{1}{\zeta-z}=\dfrac{1}{\zeta-\alpha-z+\alpha}=\dfrac{1}{(\zeta-\alpha)-(z-\alpha)}
$$
となる。
ここで、$\zeta\in C_2$であれば$\lvert z-\alpha\rvert&lt;\lvert \zeta-\alpha\rvert$であるから、
$$
\dfrac{1}{(\zeta-\alpha)-(z-\alpha)}=\dfrac{1}{\zeta-\alpha}\dfrac{1}{1-(z-\alpha)/(\zeta-\alpha)}\\
=\dfrac{1}{\zeta-\alpha}\sum_{n=0}^\infty(\dfrac{z-\alpha}{\zeta-\alpha})^n
$$
が収束する。
一方で、$\zeta\in C_1$であれば$\lvert z-\alpha\rvert&gt;\lvert \zeta-\alpha\rvert$であるから、
$$
\dfrac{1}{(\zeta-\alpha)-(z-\alpha)}=-\dfrac{1}{z-\alpha}\dfrac{1}{1-(\zeta-\alpha)/(z-\alpha)}\\
=\dfrac{1}{z-\alpha}\sum_{n=0}^\infty(\dfrac{\zeta-\alpha}{z-\alpha})^n
$$
が収束する。

以上から、
$$
f(z)=-\frac{1}{2\pi i}\int_{C_1}\frac{f(\zeta)}{\zeta-z}d\zeta+\frac{1}{2\pi i}\int_{C_2}\frac{f(\zeta)}{\zeta-z}d\zeta\\
=\frac{1}{2\pi i}\int_{C_1}\frac{1}{\zeta-\alpha}\sum_{n=1}^\infty(\frac{\zeta-\alpha}{z-\alpha})^nf(\zeta)d\zeta+
\frac{1}{2\pi i}\int_{C_2}\frac{1}{\zeta-\alpha}\sum_{n=0}^\infty(\frac{z-\alpha}{\zeta-\alpha})^nf(\zeta)d\zeta\\
=\frac{1}{2\pi i}\sum_{n=1}^\infty(\int_{C_1}(\zeta-\alpha)^{-n}f(\zeta)d\zeta)(z-\alpha)^{-n}
+\frac{1}{2\pi i}\sum_{n=0}^\infty(\int_{C_2}(\zeta-\alpha)^{-(n+1)}f(\zeta)d\zeta)(z-\alpha)^{n}
$$
となる。
これは$z$によらないから、$C_1, C_2$の半径を動かすことができ、
$$
f(z)=\sum_{n=-\infty}^\infty(\frac{1}{2\pi i}\int_{\lvert z-\alpha\rvert=r}\frac{f(\zeta)}{(\zeta-\alpha)^{n+1}}d\zeta)(z-\alpha)^n
$$
となる。

{{< hint >}}
  以下は$z=0$中心の展開を考える。
  $$
  f(z)=\dfrac{3z^3+2z^2+z-1}{z^2}=-z^{-2}+z^{-1}+2+3z
  $$
  で、$z=0$は$2$位の極で留数$1$である。

  $$
  f(z)=e^{1/z}=\sum_{n=0}^\infty\frac{1}{n!}z^{-n}
  $$
  であり、真性特異点。

  $$
  f(z)=\dfrac{e^z}{z^4}=z^{-4}+z^{-3}+\frac{1}{2}z^{-2}+\frac{1}{6}z^{-1}+\cdots
  $$
  であり、$4$位の極、留数は$\dfrac{1}{6}$である。

  $$
  f(z)=\dfrac{1}{z^4+z^2}=z^{-2}\dfrac{1}{z^2+1}=z^{-2}(1-z^2+z^4+\cdots)
  $$
  であり、$2$位の極、留数は$0$である。

  $$
  f(z)=\dfrac{e^z-1}{z}=1+\frac{1}{2}z+\cdots
  $$
  であり、除去可能特異点。
{{< /hint >}}

## 孤立特異点の分類

孤立特異点の分類とローラン級数展開による特徴づけについて。
除去可能特異点、極、真性特異点の三種類に分類する。

主要部が$0$なとき除去可能特異点、有限和であれば極、無限和であれば真性特異点である。
極に対してはローラン級数展開の係数について$a_n\neq0$となる最小の$n$が定まる。
$-n$を極の位数という。
$\alpha$で$-n$位の極をもつという。

$z\to\alpha$での振る舞い。
除去可能特異点なら有限値に収束、極なら$\infty$に発散、真性特異点なら近づき方によっていろんな値になる。

{{< hint >}}

    $z=a$が$f(z)$の孤立特異点であり、$z=a$を含めた領域で正則な函数$g(z)$が存在して、
    $z\neq a$では$f(z)=g(z)$であるとき、$z=a$は除去可能特異点であるという。
{{< /hint >}}
  
要するに除去可能特異点は見かけ上特異点のようになっているが、実際のところ特異点ではないものである。

{{< hint >}}

    $\dfrac{e^z-1}{z}, \dfrac{\sin z}{z}$など。
    $z=0$が除去可能特異点。
{{< /hint >}}

$0&lt;\lvert z-\alpha\rvert&lt;\epsilon$ならば$\lvert f(z)\lvert\leq M$となる$\epsilon$と$M$が存在することが同値。

{{< hint >}}  
    $z=a$が$f(z)$の孤立特異点であり、$\lim_{z\to a,z\neq a}f(z)=\infty$であるとき、$z=a$を極という。
  
    また、$z=a$が$f(z)$の極であるとき、ある整数$n$について$(z-a)^nf(z)$は$z=a$まで正則な関数となる。
    このような$n$で最小のものを$z=a$の極の位数という。

    $z=a$が極の場合には主要部が有限和となる。
{{< /hint >}}

極の異なる定義。
主要部が$0$でなく、有限和なとき。
$a_n\neq0$なる最小の$n$について$-n$を位数といい、$a_{-1}$を留数という。
このとき、$f(z)=\dfrac{g(z)}{(z-\alpha)^n}$と正則な$g(z)$を用いてかけ、正則関数の日である。
逆に正則関数の比は分母が$0$になるところで極をもつ。

{{< hint >}}
    $f(z)=\dfrac{1}{z(z-1)}$
    は$z=0$で主要ぶが$-z^{-1}$で極
{{< /hint >}}

いずれでもない場合、真性特異点という。
$e^{-1/x}$とか$\sin\dfrac{1}{z}$とか？
主要ぶが無限話

$\alpha$が$f$の真性特異点のとき、
$z\to\alpha$をうまく近づけると$f(z)$をどんな値にも近づけられる。


{{< hint >}}
    領域$\Omega$で極を除いて正則な関数を有理形関数という。
{{< /hint >}}

{{< hint >}}
    正則関数の比で表される関数は有理型関数である。
{{< /hint >}}


{{< hint >}}
    $f(z)=\dfrac{z^2-3z+2}{z^2(z^2-1)}$の孤立特異点（正則な点？）を求めよ。
    単に正則な点と除去可能特異点の違いは？
    約分をしない式で定義されていることがポイント。
{{< /hint >}}

{{< hint >}}
    $\dfrac{1}{z^2(z-1)^2}$は$z=0, 1$にそれぞれ$2$位の極。
    ローラン級数展開を計算しよう。
{{< /hint >}}
