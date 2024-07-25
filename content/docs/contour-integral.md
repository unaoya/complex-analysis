+++
title = '複素線積分'
date = 2024-07-14T23:10:31+09:00
draft = false
+++

# 複素線積分

ここでは複素関数の**線積分**について解説する。
複素平面の部分集合$U\subset \mathbb{C}$上定義された複素関数$f:U\to \mathbb{C}$と$U$内の曲線$\gamma:[a,b]\to U$に対し、
線積分$$\int_Cf(z)dz$$を定義することができる。

## 線積分の定義

「微分形式の引き戻し」により計算する。
置換積分、積分の変数変換公式、という観点で積分を定義する。

曲線の長さ、あるいはベクトル場の線積分などを必要に応じて復習する。

$dz=dx+idy$で、$f(z)dz$という複素係数の$\CC$上の微分形式を、
$\gamma:t\mapsto z(t)$によって閉区間に引き戻す。
$\gamma^\ast(dz)=d(\gamma(t))=\gamma\'(t)dt$となる。
これを$z\'(t)$とも書く。
$z(t)=x(t)+iy(t)$と成分でかくと、$z\'(t)=x\'(t)+iy\'(t)$であり、
$dz=z\'(t)dt=x\'(t)dt+iy\'(t)dt$となる。

{{< hint info >}}
$C$を$U$内の向きのついた区分的$C^1$曲線とし、$\gamma:[a,b]\to U$をそのパラメータづけとする。
このとき、$f$の$C$にそった線積分を
$$
\int_C f(z)dz=\int^b_af(\gamma(t))\gamma'(t)dt
$$
と定義する。  
{{< /hint >}}

これは$\RR^2$における線積分と本質的な違いはない。
値が複素数になるが実部と虚部に分ければそれぞれ実数値の線積分である。
$dz=dx+idy$と解釈できる。
線積分の定義においては、$f$が正則でなくともよい。
あとで述べるように線積分は曲線のパラメータづけ$\gamma$には依存しない。
このことは、積分の変数変換の公式により証明できる。    

リーマン和を用いて定義することもできる？
極限の取り方に注意が必要？
パラメータを用いて極限をとる？
$\lim\sum_{i=1}f(z_{i+1}-f(z_i))(z_{i+1}-z_i)$として定義する。

## 線積分の計算例

## 線積分の基本的な性質

置換積分の公式によれば、複素線積分の値はパラメータの表示の仕方によらない。
より正確には、向きを保つ変換によって、複素線積分の値は変わらない。

{{< hint >}}
曲線$C$のパラメータ表示$z(t)$を単調増加で滑らかな関数$t=\phi(s)$を用いて、$w(s)=z(\phi(s))$に置き換える。
ここで単調増加であることはポイント。
次に述べる向きに関係する。

置換積分の公式と、合成関数の微分公式を用いることで
$$
\int_a^bf(z(t))z'(t)dt=\int_c^df(z(\phi(s)))z'(\phi(s))\phi'(s)ds=\int_c^df(w(s))w'(s)ds
$$
と計算できる。
つまり、どちらのパラメータ表示でも同じ結果が得られる。
{{< /hint >}}

曲線の向きを逆にすると線積分の値は$-1$倍される。
曲線$C$の向きを逆にした曲線を$-C$と表すことにする。
ここでは、$-C$は$C$のパラメータづけ$z(t), a\leq t\leq b$に対して$z(-t), -b\leq t\leq -a$で定まるもの。

{{< hint info >}}
このとき
$$
\int_{-C}f(z)dz=-\int_Cf(z)dz
$$
が成り立つ。
{{< /hint >}}

{{< hint >}}
$\dfrac{d}{dt}(z(-t))=-\dfrac{d}{dt}z(t)$であるから、積分の値は$-1$倍される。
{{< /hint >}}


    曲線の分割と結合。


{{< hint >}}
    $$
    \int_Cf(z)dz=\int_{C_1}f(z)dz+\int_{C_2}f(z)dz
    $$
{{< /hint >}}

このことを用いて区分的に滑らかな曲線上の線積分を定めることができる。

積分値の絶対値評価については次が成り立つ。

{{< hint >}}
$$
\left\lvert\int_Cf(z)dz\right\rvert\leq\int_C\lvert f(z)\rvert \lvert dz\rvert
$$
が成り立つ。
{{< /hint >}}


  $\lvert dz\rvert$とは？
  $\sqrt{dx^2+dy^2}$であり、$z=z(t)$による引き戻しは$z'(t)dt$である。

積分と極限の順序交換については次が成り立つ。

{{< hint info >}}
連続な複素関数の列$\\{f_n\\}\_{n\in\mathbb{N}}$が「曲線$C$上で」$f$に一様収束するとする。
このとき、
$$
\lim_{n\to\infty}\int_Cf_n(z)dz=\int_C\lim_{n\to\infty}f_n(z)dz=\int_Cf(z)dz
$$
がなりたつ。
{{< /hint >}}

## 線積分の計算例


    簡単な線積分の計算例を見ていこう。
    単位円や正方形など簡単な図形で計算する。
    一次式など。
    不定積分がある場合。
    ポテンシャルがあれば始点と終点のみで決まることなど。


{{< hint >}}
  定数関数$f(z)=1$の線積分を調べる。
{{< /hint >}}

{{< hint >}}
    点$O$を$z=0$、点$A$を$z=1$、点$B$を$z=1+i$で定める。
    関数$f(z)=z$について、線分$OA, AB, BO$に沿った線積分を計算しよう。
  
    それぞれのパラメータづけを
    \begin{align*}
      \gamma_1(t)&=t, &t\in[0,1]\\
      \gamma_2(t)&=1+ti, &t\in[0,1]\\
      \gamma_3(t)&=(1+i)(1-t), &t\in[0,1]\\
    \end{align*}
    とする。
    
    \begin{align*}
      \int_{OA}f(z)dz
      &=
      \int_0^1tdt\\
      &=
      \frac{1}{2}\\
      \int_{AB}f(z)dz
      &=
      \int_0^1(1+ti)idt\\
      &=
      i-\frac{1}{2}\\
      \int_{BO}f(z)dz
      &=
      \int_0^1(1+i)(1-t)(-(1+i))dt\\
      &=
      -\frac{1}{2}(1+i)^2\\
      &=
      -i
    \end{align*}
    となる。
  
    特に三つの積分の和が$0$となることに注目しよう。
{{< /hint >}}


{{< hint >}}
    $g(z)=z^2, h(z)=\bar{z}$について上と同じ線分に沿った線積分を計算せよ。
    $OA, AB, BO$のパラメータは上と同様に与える。
  
    まず$g(z)=z^2$について。
    \begin{align*}
      \int_{OA}g(z)dz
      &=
      \int_0^1t^2dt\\
      &=
      \frac{1}{3}\\
      \int_{AB}g(z)dz
      &=
      \int_0^1(1+ti)^2idt\\
      &=
      -1+\frac{2}{3}i\\
      \int_{BO}g(z)dz
      &=
      \int_1^0t(1+i)^2(1-t)^2(-(1+i))dt\\
      &=
      -\frac{1}{3}(1+i)^3\\
      &=
      -\frac{1}{3}(2i-2)
    \end{align*}
  
    次に$h(z)=\bar{z}$について。
    \begin{align*}
      \int_{OA}h(z)dz
      &=
      \int_0^1tdt\\
      &=
      \frac{1}{2}\\
      \int_{AB}h(z)dz
      &=
      \int_0^1(1-ti)idt\\
      &=
      i+\frac{1}{2}\\
      \int_{BO}h(z)dz
      &=
      \int_0^1(1-i)(1+t)(-(1+i))dt\\
      &=
      -2\int_0^1(1+t) dt\\
      &=
      -3
    \end{align*}  
{{< /hint >}}

{{< hint >}}
    $C$を反時計回り単位円周とし、$\gamma(t)=\exp(2\pi it), t\in[0,1]$をそのパラメータづけとする。
    \begin{align*}
      \int_C dz
      &=\int_0^12\pi i\exp(2\pi it)dt\\
      &=[\exp(2\pi it)]^1_0\\
      &=0
    \end{align*}      
{{< /hint >}}

{{< hint >}}
    $C$を反時計回り単位円周とする。
    \begin{align*}
      \int_Cz^ndz
    \end{align*}
    を計算せよ。

    上と同様にパラメータづけを与える。
    $n\neq-1$であれば
    \begin{align*}
      \int_Cz^ndz
      &=\int_0^1\exp(2n\pi it)2\pi\exp(2\pi it)dt\\
      &=[\frac{1}{n+1}\exp(2(n+1)\pi it)]^1_0\\
      &=0
    \end{align*}
    である。
    $n=-1$のとき、
    \begin{align*}
      \int_C\frac{1}{z}dz
      &=
      \int_0^1\exp(-2\pi it)2\pi i\exp(2\pi it)dt\\
      &=
      \int_0^12\pi idt\\
      &=2\pi i
    \end{align*}
    となる。  
{{< /hint >}}


    $\dfrac{dz}{z}$を$z=\dfrac{1}{w}$で変換すると、$dz=-\dfrac{dw}{w^2}$であるから$-\dfrac{dw}{w}$となる。
    一方で$\dfrac{dz}{z^2}$であれば$-dw$である。
    ここに$n=-1$の特殊性がある。    


{{< hint >}}
    $C$を反時計回り単位円周とする。
    \begin{align*}
      \int_C\bar{z}dz
    \end{align*}
    を計算せよ。

    上と同様にパラメータづけを与える。
    \begin{align*}
      \int_C\bar{z}dz
      &=\int_0^1\exp(-2\pi it)2\pi i\exp(2\pi t)dt\\
      &=2\pi i
    \end{align*}    
{{< /hint >}}

{{< hint >}}
    $C$を中心$a$で半径$r$の反時計回り円周とする。
    \begin{align*}
      \int_C(z-a)^ndz
    \end{align*}
    を計算せよ。
  
    $\gamma(t)=\exp(2\pi it)+a, t\in[0,1]$をそのパラメータづけとする。
    \begin{align*}
      \int_C(z-a)^ndz
      &=
      \begin{cases}
        2\pi i& n=-1\\
        0& n\neq-1
      \end{cases}
    \end{align*}  
{{< /hint >}}

## 複素線積分の基本的な性質

{{< hint >}}
  $1$から$-1$への上半円を$z(t)=e^{it}, 0\leq t\leq \pi$でパラメータ表示するか、
  $w(s)=e^{2is}, 0\leq s\leq\dfrac{pi}{2}$でパラメータ表示するか。
{{< /hint >}}

{{< hint >}}
  $C$を単位円の反時計回り向きとする。
  パラメータづけを$z(t)=e^{it}, 0leq t\leq 2\pi$で与える。
  これに対して、$-C$は$w(t)=e^{-it}, -\pi\leq t\leq 0$である。
{{< /hint >}}






    積分路の変更。


{{< hint >}}
  図が必要。
  $C$を円として、その直径を引いて二つに分けたものを$C_1, C_2$とする。
  向きを「反時計回り」につけることで、
  $$
  \int_C=\int_{C_1}+\int_{C_2}
  $$
  となる。
{{< /hint >}}

{{< hint >}}
  同心円$C, C'$をその「直径」で二つに分けて$C_1, C_2$とする。
  向きを「反時計回り」につけることで
  $$
  \int_{C_1}+\int_{C_2}=\int_C-\int_{C'}
  $$
  となる。
{{< /hint >}}

{{< hint >}}
  長方形$R$を$4$分割して、それぞれを$R_1, R_2, R_3, R_4$とする。
  向きを「反時計回り」につけることで
  $$
  \int_R=\sum_i\int_{R_i}
  $$
  となる。
{{< /hint >}}



</body>
</html>