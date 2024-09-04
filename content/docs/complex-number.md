---
title: "複素数"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# 複素数と複素平面

複素解析では定義域と値域が複素数であるような関数について調べる。
特に微分可能な関数を正則関数といい、正則関数の性質を調べるのが目的である。

複素数と複素平面．複素微分
複素数と複素平面について復習した後，複素関数の連続性と微分を解説する．

## 複素数と四則

複素数とは、実数の組$x, y$を用いて定まる数$z=x+yi$のこと。
$x$を$z$の実部といい$Re(z)$で表す。
$y$を$z$の虚部といい$Im(z)$で表す。
また、$i$を虚数単位という。
あとで見るように、$i^2=-1$となるよう複素数の積を定める。

複素数全体の集合を$\CC$と表す。
$z\in\CC$であれば、一意的に実数$x, y$を用いて$z=x+yi$と表すことができる。
$x$を$z$の実部と呼び$Re(z)$と表す。
$y$を$z$の虚部と呼び$Im(z)$と表す。
複素数全体の集合は、集合としては$\RR^2$と思うことができる。
二つの複素数が一致することは、実部と虚部が共に等しいこと。
つまり、$z=x+yi, z'=x'+y'i$について、$z=z'$であることと$x=x'$かつ$y=y'$であることが同値。

## 複素数の四則演算

足し算と引き算は$\RR^2$のものと同じ。
実部同士と虚部同士をそれぞれ足し引きすればいい。
$$
	(a+bi)+(c+di)=(a+c)+(b+d)i\\\\
	(a+bi)-(c+di)=(a-c)+(b-d)i
$$

掛け算は次のように定める。
$$
	(a+bi)(c+di)=(ac-bd)+(ad+bc)i
$$
これは、$i^2=-1$かつ実双線形という条件で特徴づけられる。

割り算は？
$$
	(a+bi)/(c+di)=\\
$$
いずれも、右辺を用いて左辺を定めるという式になっていることに注意。

この四則演算について、通常の数の和や積と同様に結合法則や交換法則、分配法則が成り立つ。

## 複素共役

$z\in\CC$に対し、$z=a+bi$であるとき$\bar{z}\in\CC$を$\bar{z}=a-bi$により定める。
これを$z$の複素共役という。
$z$と$\bar{z}$から$z$の実部虚部を復元できる。
$x=Re(z)=\dfrac{1}{2}(z+\bar{z}), y=Im(z)=\dfrac{1}{2}(z-\bar{z})$である。

複素共役と四則演算の関係について。
複素共役をとる操作と四則演算は順序を入れ替えることができる。
すなわち以下が成り立つ。

$$
	\overline{\alpha\pm\beta}=\overline{\alpha}\pm\overline{\beta}\\
	\overline{\alpha\beta}=\overline{\alpha}\overline{\beta}\\
	\overline{\left(\dfrac{\alpha}{\beta}\right)}=\dfrac{\overline{\alpha}}{\overline{\beta}}
$$

また、複素共役を2回とることで元に戻る。

$z$が実数であることは、$z=\bar{z}$と同値である。

共役を用いて実部と虚部を記述できる。
$$
	Re(z)=\frac{z+\overline{z}}{2}\\
	Im(z)=\frac{z-\overline{z}}{2i}
$$

## 複素数の絶対値
複素数$z=x+yi$に対し、
$$
\lvert z\rvert=\sqrt{z\overline{z}}=\sqrt{x^2+y^2}
$$
と定義し、これを$z$の絶対値と呼ぶ。

$\lvert z\rvert=1$のとき、$\bar{z}=\dfrac{1}{z}$である。

代数学の基本定理

## 極形式

複素数の積と複素平面の関係については極形式の方が見やすい。
絶対値が積、偏角が和に対応する。

## 複素平面

複素数$z=x+yi$に対して$(x,y)$という点を対応させる。

複素平面。
複素数を$xy$座標平面にプロットできる。
実軸と虚軸。
複素数の和は平面ベクトルの和と同じ。

複素共役は$x$軸鏡映。

複素数の和と絶対値に関しては、三角不等式が成り立つ。
距離、位相に関連して。
収束などを議論する上で重要な性質。
$$
\lvert z\rvert-\lvert w\rvert\leq\lvert z+w\rvert\leq\lvert z\rvert+\lvert w\rvert
$$

$0$でない複素数$z$に対し、その偏角とは、

$0$でない複素数$z$の極形式とは、
その絶対値を$r$、偏角を$\theta$として
$$
z=r(\cos\theta+i\sin\theta)
$$
のことをいう。

絶対値や偏角と和や積の関係。

極座標表示。
$z=x+yi$に対し、$r=\lvert z\rvert=\sqrt{x^2+y^2}$とおき、
$\theta$を偏角とする。
つまり、$\theta=\arctan\dfrac{x}{y}$であり、$r\cos\theta=x, r\sin\theta=y$で定まるもの。
$\theta$は$2\pi$の不定性がある。
$z=r(\cos\theta+i\sin\theta)$を極形式と呼ぶ。

積と回転。
複素数の積に対し、絶対値は積、偏角は和になる。
$z_1=r_1(\cos\theta_1+i\sin\theta_1), z_2=r_2(\cos\theta_2+i\sin\theta_2)$とすると、
$z_1z_2=r_1r_2(\cos(\theta_1+\theta_2)+i\sin(\theta_1+\theta_2))$となる。
これは加法定理から証明できる。

{{< hint >}}
	$\alpha=1+i=\sqrt{2}(\cos\dfrac{\pi}{4}+i\sin\dfrac{\pi}{4}),
	\beta=\sqrt{3}+i=2(\cos\dfrac{\pi}{6}+i\sin\dfrac{\pi}{6})$に対し、
	$\alpha\beta=2\sqrt{2}(\cos\dfrac{5}{12}\pi+i\sin\dfrac{5}{12}\pi)$となるため、
	$\cos\dfrac{5}{12}\pi, \sin\dfrac{5}{12}\pi$を求めることができる。
{{< /hint >}}

複素平面における円や直線について。
$z-\bar{z}=0$が実軸、$z+\bar{z}=0$が虚軸である。
$\alpha z-\bar{\alpha z}=0$が原点と$z=\bar{\alpha}$を通る直線。
$\alpha(z-\beta)-\bar{\alpha}(\bar{z}-\bar{\beta})=0$が$z=\beta$を通る直線。

$\lvert z\rvert=r$が原点中心で半径$r$の円。
$\lvert z-\alpha\rvert=r$が$z=\alpha$が中心で半径$r$の円。

$\lvert\dfrac{az+b}{cz+d}\rvert=k$を整理する。
$$
	\lvert az+b\rvert=k\lvert cz+d\rvert\\
	\lvert a\rvert\lvert z+\dfrac{b}{a}\rvert=k\lvert c\rvert\lvert z+\dfrac{d}{c}\rvert
	\lvert z+\dfrac{b}{a}\rvert:\lvert z+\dfrac{d}{c}\rvert=\lvert a\rvert:k\lvert c\rvert
$$
となるので、これはアポロニウスの円である。
一次分数変換により円と円が対応する。

ドモアブルの公式。
$z=r(\cos\theta+i\sin\theta)$に対し、
$z^n=r^n(\cos n\theta+i\sin n\theta)$となる。

$1$の$n$乗根。
$z=r(\cos\theta+i\sin\theta)$に対し、$z$の$n$乗根は
$$
	r^{1/n}(\cos(\dfrac{\theta}{n}+\dfrac{2\pi}{n}k)+i\sin(\dfrac{\theta}{n}+\dfrac{2\pi}{n}k))
$$
である。

特に$1$の$n$乗根は、整数$k$を用いて
$$
\cos\frac{2\pi}{n}k+i\sin\frac{2\pi}{n}k
$$
と表すことができる。

また、一般の$\alpha$の$n$乗根は、$1$の$n$乗根をかけることで全て得られる。