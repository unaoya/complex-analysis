---
title: "コーシーの積分定理"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# コーシーの積分定理

ここではコーシーの積分定理について説明する。

{{< hint >}}
複素平面内の領域$U\subset \mathbb{C}$上の正則関数$f:U\to\mathbb{C}$と、
$U$内の閉曲線$C$が適切な条件を満たすとき、以下の式が成り立つ。

$$
  \int_Cf(z)dz=0
$$
{{< /hint >}}

## コーシーの積分定理

いくつかの関数について閉曲線での複素線積分が$0$になったが、これは偶然ではない。
例えば$f(z)$が正則で$f\'(z)$が連続であれば、以下のようにグリーンの定理を用いて証明できる。

$f$が$D$上の正則関数で$f\'$が連続であると仮定する。
$C$は自分自身と交わらない連続閉曲線で、ある有界領域$B$の境界である。
$B\subset D$とする。

このとき、複素線積分の定義と、グリーンの定理から、$f(z)=u(x,y)+iv(x,y)$に対して
$$
  \int_Cf(z)dz=\int_C(u(x,y)dx-v(x,y)dy)+i\int_C(u(x,y)dy+v(X,y)dx)=-\int\int_B(v_x(x,y)+u_y(x,y))dxdy+i\int\int_B(u_x(x,y)-v_y(x,y))dxdy
$$
となる。

さらにコーシーリーマン方程式から
$$
  v_x+u_y=0\\\\
  u_x-v_y=0
$$
となるので、結局
$$
  \int_Cf(z)dz=0
$$
となる。

実は導関数の連続性を仮定せずとも成立する。
理論上はこの結果が重要で、これのおかげで正則関数の導関数がまた正則関数であることが導かれる。

## 長方形に対するコーシーの積分定理

{{< hint >}}
  $R\subset\mathbb{C}$を長方形領域とし、$f$は$R$の境界および内部で正則であるとする。
  このとき、
  $$
    \int_{\partial R}f(z)dz=0
  $$
  である。
{{< /hint >}}

## 原始関数の存在

コーシーの積分定理を用いて原始関数の存在を証明する。
（これは単連結領域であることが必要？）

$f$を円板内部で正則な関数とする。
$$
  F(z)=\int^z_af(z)dz
$$
とおく。
これが経路によらないのはなぜか？

これが正則になるのはなぜか？
また、原始関数であるのはなぜか？
積分経路を工夫して計算する。
$x$軸と並行な$C_2$と$y$軸と平行な$C_1$を用いて$a$と$z$を繋ぐ。
$$
  \frac{\partial}{\partial x}F(z)=\frac{\partial}{\partial x}(\int_{C_1}f(z)dz+\int_{C_2}f(z)dz)= f(z)
$$
となり、同様にして
$$
  \frac{\partial}{\partial y}F(z)=if(z)
$$
となる。
よって、コーシーリーマン方程式により、$F(z)$が正則であり、$F\'(z)=f(z)$であることもわかる。

## 積分路と原始関数

線積分の値が積分路によらず始点と終点のみで決まる場合がある。
$\alpha, \beta\in\mathbb{C}$を結ぶ任意の曲線$C_1, C_2$に対して
$$
  \int_{C_1}f(z)dz=\int_{C_2}f(z)dz
$$
が成り立つ。

あるいは、任意の閉曲線$C$について
$$
  \int_Cf(z)dz=0
$$
が成り立つ。

これは関数$f$がどのような性質を持つときか。

{{< hint >}}
  $f(z)=z^n$など。
{{< /hint >}}

$f$が原始関数を持つとき、（単連結領域じゃなくても？）線積分は経路によらない。

{{< hint >}}
  $F\'(z)=f(z)$であるとする。
  このとき、
  $$
  \frac{d}{dt}F(z(t))~F\'(z(t)z\'(t)=f(z(t)))z\'(t)
  $$
  である。
  よって、
  $$
  \int_Cf(z)dz=\int^b_af(z(t))z\'(t)dt=\int_a^b(\frac{d}{dt}F(z(t)))dt=F(b)-F(a)
  $$
  となる。
  つまり、$C$の始点$a$と終点$b$のみで定まる。
  （原始関数は積分定数の不定性があるが、それは消える。）
{{< /hint >}}

## 一般的なコーシーの積分定理

より一般の状況における積分定理を述べるため、いくつか言葉を用意しよう。

{{< hint >}}
  空でない連結開集合$\Omega\subset\mathbb{C}$を領域という。
{{< /hint >}}

ここで$\Omega$が連結であるとは$\Omega$の部分集合で開集合かつ閉集合であるものが$\Omega$自身と$\emptyset$のみであることをいう。

{{< hint >}}
  閉曲線$C$の$z=a$についての回転数$n(C,a)$を
  $$
    n(C,a)=\frac{1}{2\pi i}\int_C\frac{dz}{z-a}
  $$
  で定義する。
{{< /hint >}}

{{< hint >}}
  反時計回りの単位円周を$C$としたとき、$n(C,0)=1, n(C,2)=0$である。
{{< /hint >}}

閉曲線の形式的な和をサイクルという。

{{< hint >}}
  領域$D$内のサイクル$C$が、$D$に関して$0$にホモローグであるとは、
  $D$の補集合の任意の点$a$に対し、$n(C,a)=0$であること。
{{< /hint >}}

{{< hint >}}
  $D=\mathbb{C}$とし、$C$を反時計回りの単位円周とするとこれは$D$に関して$0$にホモローグ。
  一方で$D=\mathbb{C}\setminus\{0\}$とすると、この$C$は$D$に関して$0$にホモローグではない。
{{< /hint >}}

この概念を用いて、コーシーの積分定理をより強い形で述べる。

{{< hint >}}
  $f$が領域$D\subset \mathbb{C}$で正則とする。
  $D$内でホモローグ$0$な任意のサイクル$C$に対し、次が成り立つ。
  $$
    \int_Cf(z)dz=0
  $$
{{< /hint >}}

ここではこれについて証明はしない。
重要な点は、コーシーの積分定理を成立させるためにホモローグ$0$という位相幾何的な条件を考えることにある。  

積分路の変更。
$C_1$と$C_2$が$D$内で連続変形できれば、
$$
  \int_{C_1}f(z)dz=\int_{C_2}f(z)dz
$$
となる。

単純閉曲線とは。始点と終点が同じで、自己交差を持たないもの。

曲線の連続変形とは。

## コーシーの積分定理を用いた積分計算


{{< hint >}}
  $C$を単位円周で正の向きとする。
  $$
  \int_C\frac{1}{z-a}dz
  $$
  を$a\notin C$の値で場合わけして求める。
  中か外か。
  $$
  \int_C\dfrac{1}{z}dz=2\pi i
  $$
  を思い出す。
{{< /hint >}}

{{< hint >}}
  $C$を楕円$a\cos t+ib\sin t$とする。
  このとき、
  $$
  \int_Cz^ndz
  $$
  を求めよ。
{{< /hint >}}

{{< hint >}}
  $C$を単位円として、
  $$
  \int_C\frac{1}{z(z-2i)}dz, \int_C\frac{1}{z^2-2z}dz
  $$
  を計算する。
{{< /hint >}}

{{< hint >}}
  $C$を中心$\alpha$で半径$r$の円を反時計回りに向きをつけたものとして、
  $$
  \int_C\frac{1}{z^2+1}dz
  $$
  の値がどうなるか、場合わけして計算する。
{{< /hint >}}

## コーシーの積分定理の証明

長方形の場合にのみ、簡単に証明を見てみよう。
大雑把に言えば、正則関数なので十分小さい領域では一次式で近似でき、
一次式の積分は直接計算する、という方法で証明する。

{{< hint >}}
  $R$を$a\leq x\leq b, c\leq y\leq d$で定義された長方形とし、その周$\partial R$に反時計回りに向きをつける。
  $f(z)$が$R$で正則であれば
  $$
    \int_{\partial R}f(z)dz=0
  $$
  が成り立つ。
{{< /hint >}}

証明の方針としては、長方形$R$を細分していき、$f(z)$を一次関数で近似した積分値によって評価する。

長方形$S$の周での積分値を$\eta(S)$と略記する。
つまり、
$$
  \int_{\partial S}f(z)dz=\eta(S)
$$
とする。

まず、$4$つの合同な長方形に分割し、それらを$R^1, R^2, R^3, R^4$と仮に名付ける。
すると、
$$
  \eta(R)=\eta(R^1)+\eta(R^2)+\eta(R^3)+\eta(R^4)
$$
である。
すると、$R^1$から$R^4$のうちの少なくとも一つは
$$
  \lvert\eta(R^i)\rvert\geq\lvert\eta(R)\rvert
$$
を満たす。
これを$R_1$と書くことにしよう。

これを同様に繰り返すことで$R_n$を定義する。
つまり、
$$
  \lvert\eta(R_n)\rvert\geq\frac{1}{4}\lvert\eta(R_{n-1})\rvert
$$
が成立するように長方形をどんどん小さくとっていく。

すると
$$
  \lvert \eta(R_n) \rvert\geq\frac{1}{4^n}\lvert \eta(R) \rvert
$$
が成り立つ。

この長方形はある点$z_\ast$に収束する。
正確にいうと、任意の$\delta$に対して十分大きな$n$について$R_n$は$\lvert z-z_\ast \rvert&lt;\delta$に含まれる。
このとき、$f$が$z_\ast$で正則であるから、微分係数の定義から、
任意の$\epsilon>0$に対し、$\delta$を適当に取ることで、$0&lt;\lvert z-z_\ast \rvert&lt;\delta$に対し
$$
  \lvert f(z)-f(z_\ast)-(z-z_\ast)f\'(z_\ast) \rvert&lt;\epsilon\lvert z-z_\ast \rvert
$$
が成り立つようにできる。

長方形の場合に一次式の積分を直接計算すると
$$
  \int_{\partial R_n}dz=0\\\\
  \int_{\partial R_n}zdz=0
$$
となる。

これにより、
$$
  \eta(R_n)=\int_{\partial R_n}f(z)dz
  =\int_{\partial R_n}(f(z)-f(z_\ast)-(z-z_\ast)f\'(z_\ast))dz
$$
が成り立つ。
上の不等式により
$$
  \lvert \eta(R_n) \rvert\leq\epsilon\int_{\partial R_n}\lvert z-z_\ast \rvert\lvert dz \rvert
$$
となる。

ここで$\lvert z-z_\ast \rvert$は$R_n$の対角線の長さ$d_n$より小さく、また$R_n$の周の長さを$L_n$とすると、
$$
  \epsilon\int_{\partial R_n}\lvert z-z_\ast \rvert\lvert dz \rvert\leq d_nL_n
$$
となる。

$R$の対角線の長さ$d$、周の長さ$L$とすると、$d_n=\dfrac{1}{2^n}d, L_n=\dfrac{1}{2^n}L$であるから、
$$
  \lvert \eta(R_n) \rvert\leq\frac{1}{4^n}dL\epsilon
$$
となり、
$$
  \lvert \eta(R) \rvert\leq dL\epsilon
$$
が成立する。

これが任意の$\epsilon>0$で成り立つので
$$
  \eta(R)=0
$$
が証明できた。
