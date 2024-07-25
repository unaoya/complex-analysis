---
title: "べき級数"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# べき級数について

べき級数の収束半径，べき級数の様々な演算に関して解説する．
また，正則関数のべき級数展開について解説する．

冪級数とは。
$\alpha\in\mathbb{C}$に対し、$\alpha$を中心とする冪級数とは、$a_n\in\mathbb{C}$を用いて定まる
$$
\sum_{n=0}^\infty a_n(z-\alpha)^n
$$
のこと。
収束について。
正確には、$\lim_{N\to\infty}\sum_{n=0}^Na_n(z-\alpha)^n$である。

{{< hint >}}
  $$
  \sum_{n=0}^\infty z^n=1+z+z^2+\cdots
  $$
  は$0$を中心とした冪級数。
  これは$\lvert z\rvert&lt;1$の範囲で、$\dfrac{1}{1-z}$に収束する。
{{< /hint >}}

和や積、項別微分と項別積分

$\sum_na_nz^n, \sum_nb_nz^n$が収束するならば、$\sum_n(a_n+b_n)z^n, \sum_nca_nz^n$が収束する。
積は$\sum_n(\sum_ka_{n-k}b_k)z^n$が収束する？

{{< hint >}}
  冪級数
  $$
  \sum_{n=0}^\infty a_nz^n
  $$
  が絶対収束するとは、
  $$
  \sum_{n=0}^\infty\lvert a_n\rvert\lvert z\rvert^n
  $$
  が収束することをいう。
{{< /hint >}}

冪級数が絶対収束するなら収束する。

{{< hint >}}
  べき級数の収束半径。
  $\sum_n\lvert a_n\rvert \lvert z\rvert^n$が収束する$\lvert z\rvert$の上限を$R$とする。
  これが収束半径。
  $\lvert z\rvert&lt;R$で絶対収束し、$\lvert z\rvert>R$で発散する。
  $\lvert z\rvert=R$においてはさまざまな可能性がある。
{{< /hint >}}

{{< hint >}}
  収束半径の計算方法。
  $\sum_{n=0}^\infty a_nz^n$の収束半径$R$は
  $$
  \limsup_{n\to\infty}\sqrt[n]{\lvert a_n\rvert}=\frac{1}{R}
  $$
  を満たす。
  また、以下の極限が存在すれば等式が成立する。
  $$
  \lim_{n\to\infty}\frac{\lvert a_{n+1}\rvert}{\lvert a_n\rvert}=\frac{1}{R}
  $$
{{< /hint >}}

{{< hint >}}
  $$
  \sum_{n=0}^\infty\frac{1}{n}z^n\\
  \sum_{n=0}^\infty nz^n\\
  \sum_{n=0}^\infty 8^nz^{3n}\\
  \sum_{n=0}^\infty 3^nz^{2n}\\
  \sum_{n=0}^\infty \frac{(2n)!}{(n!)^2}z^n
  $$
{{< /hint >}}

冪級数の様々な演算

{{< hint >}}
  $f(z)=\sum_{n=0}^\infty a_nz^n$の収束半径が$R>0$であるとする。
  このとき、収束円板上で連続であり、正則で、
  $$
  f\'(z)=\sum_{n=0}^\infty na_nz^{n-1}=\sum_{n=0}^\infty(n+1)a_{n+1}z^n
  $$
  が成り立ち、これも同じく収束半径$R$である。
{{< /hint >}}

{{< hint >}}
  $$
  \lvert f(z)-f(a)\rvert\leq \sum_{n=0}^\infty\lvert a_n\rvert\lvert z^n-a^n\rvert\\
  \leq\lvert z-a\rvert\sum_{n=0}^\infty n\lvert a_n\rvert r^{n-1}
  $$
  より連続。

  $$
  \frac{f(z)-f(a)}{z-a}=\sum_{n=1}^\infty a_n(z^{n-1}+\cdots+a^n)
  $$
  とおくと、これは収束し、連続である。
{{< /hint >}}

{{< hint >}}
  特に収束冪級数は解析的である。
  $f(z)=\sum_{n=0}^\infty a_n(z-\alpha)^n$とすると、$a_n=\dfrac{1}{n!}f^{(n)}(\alpha)$である。
{{< /hint >}}

## 正則関数の冪級数展開

コーシーの積分公式を用いる。
$$
f(z)=\frac{1}{2\pi i}\int_C\frac{f(\zeta)}{\zeta-z}d\zeta
$$
で$\dfrac{1}{\zeta-z}$を$z=\alpha$中心に展開する。
$w=z-\alpha$とおいて、
$$
\frac{1}{\zeta-z}=\frac{1}{\zeta-\alpha-w}=\frac{1/(\zeta-\alpha)}{1-(w/(\zeta-\alpha))}\\
=\frac{1}{\zeta-\alpha}(1+\frac{w}{\zeta-\alpha}+\frac{w^2}{(\zeta-\alpha)^2}+\cdots)\\
=\sum_{n=0}^\infty\frac{(z-\alpha)^n}{(\zeta-\alpha)^{n+1}}
$$
となる。
これが収束するか？
$\lvert\dfrac{z-\alpha}{\zeta-\alpha}\rvert&lt;1$ならよい。
一様収束すれば順序交換できる。

## 初等関数のべき級数展開
最初にロピタルの公式を述べた後，べき級数の例として初等関数のべき級数展開を紹介し，最後に解析接続の原理である一致の定理について解説する．

ロピタルの公式
$f(z), g(z)$が$z=\alpha$で解析的で、$n=0,\ldots,m-1$で$f^{(n)}(\alpha)=g^{(n)}(\alpha)=0$とする。
このとき、$g^{(m)}(\alpha)\neq0$であれば
$$
\lim_{z\to\alpha}\frac{f(z)}{g(z)}=\lim_{z\to\alpha}\frac{f^{(m)}(\alpha)}{g^{(m)}(\alpha)}
$$
が成り立つ。

{{< hint >}}
  $$
  \lim_{z\to e^{2\pi i/n}}\frac{z-e^{2\pi i/n}}{z^n-1}\\
  \lim_{z\to 0}\frac{e^z-\cos z-z}{z^2}\\
  \lim_{z\to i}\frac{\cosh(\pi z/2)}{\Log(-iz)}
  $$
{{< /hint >}}

指数関数$f(z)=e^z$の冪級数展開。
$$
e^z= \sum_{n=0}^\infty\frac{1}{n!}z^n
$$
である。
収束半径は$\infty$である。

対数関数の主値、$f(z)=\Log(1+z)$の冪級数展開。
$$
\Log(1+z)=\sum_{n=1}^\infty\frac{(-1)^{n-1}}{n}z^n
$$
収束半径は$1$

冪函数$f(z)=(1+z)^\alpha$の冪級数展開。
$$
(1+z)^\alpha=\sum_{n=0}^\infty\binom{\alpha}{n}z^n
$$
ここで、$\binom{\alpha}{n}$は一般化二項係数で、
$$
\binom{\alpha}{n}=\frac{\alpha(\alpha-1)\cdots(\alpha-n+1)}{n!}
$$
で定まるもの。

冪級数の和、積、合成

{{< hint >}}
  $f(z)=e^{2z}$を$z=0$の周りで冪級数展開して、収束半径を求める。
  $f(z)=\dfrac{1}{z^2+1}$を$z=0$の周りで冪級数展開して、収束半径を求める。
  $f(z)=\dfrac{1}{z+1}$を$z=1$の周りで冪級数展開して、収束半径を求める。
  $f(z)=\cos z=\dfrac{e^{iz}+e^{-iz}}{2}$を$z=0$の周りで冪級数展開して、収束半径を求める。
  $f(z)=\dfrac{1}{z^2-3z+2}$を$z=0$の周りで冪級数展開して、収束半径を求める。
  $f(z)=z^2\cos z^2$を$z=0$の周りで冪級数展開して、収束半径を求める。
  $f(z)=(1+z)e^z$を$z=0$の周りで冪級数展開して、収束半径を求める。
{{< /hint >}}

項別微積分を用いて冪級数展開を計算する。
$(\log(1+z))\'=\frac{1}{1+z}$を用いて$z=0$中心の$\log(1+z)$の冪級数展開と収束半径を求める。
$(\cos z)\'=-\sin z$を用いて$z=0$中心の$\sin z$の冪級数展開と収束半径を求める。
$z=0$中心の$\dfrac{1}{(1-z)^3}$の冪級数展開と収束半径を求める。
$\dfrac{1}{\cos z}$を$z=0$中心に冪級数展開し、収束半径を求める。
$\tan z$を$z=0$中心に冪級数展開し、収束半径を求める。
$\dfrac{1}{1-\sin z}$を$z=0$中心に冪級数展開し、収束半径を求める。

## 一致の定理と解析接続

ここでは正則関数の解析接続という概念を紹介する。

まずは、正則関数がテイラー展開できるという事実を証明抜きで紹介しよう。

{{< hint >}}
    $f$は領域$\Omega$で正則とする。
    このとき、$a\in\Omega$に対し、ある$\Omega$で正則な関数$f_n(z)$が存在して
    \begin{align*}
      f(z)=f(a)+f\'(a)(z-a)+\frac{f^{(2)}(a)}{2!}(z-a)^2+\cdots+\frac{f^{(n-1)}(a)}{(n-1)!}(z-a)^{n-1}+f_n(z)(z-a)^n
    \end{align*}
    となる。
  
    さらに、$z=a$を中心とする十分小さな円周$C$に対し
    \begin{align*}
      f_n(z)=\frac{1}{2\pi i}\int_C\frac{f(\zeta)}{(\zeta-a)^n(\zeta-z)}d\zeta
    \end{align*}
    となる。  
{{< /hint >}}

この事実を用いると次のことが証明できる。

{{< hint >}}
    $\Omega$で正則な関数$f(z)$について、
    $z=a$で微分係数が全て$0$だとすると$f(z)$は恒等的に$0$である。  
{{< /hint >}}

{{< hint >}}
    まず、ある円$C$の内部で$f$が恒等的に$0$であることを示す。
    微分係数が全て$0$であるとすると、任意の$n$に対しある正則関数$f_n(z)$が存在して
    \begin{align*}
      f(z)=f_n(z)(z-a)^n
    \end{align*}
    となる。
    この円$C$及びその内部における$\abs{f(z)}$の最大値を$M$とし、$C$の半径を$R$とすると、
    上の定理の剰余項の表示から
    \begin{align*}
      \abs{f_n(z)}\leq\frac{M}{R^{n-1}(R-\abs{z-a})}
    \end{align*}
    となる。
    よって
    \begin{align*}
      \abs{f(z)}\leq(\frac{\abs{z-a}}{R})^n\frac{MR}{R-\abs{z-a}}
    \end{align*}
    となる。
    ここで、$\abs{z-a}&lt;R$となるので、$n\to\infty$で右辺は$0$に収束するから$f(z)=0$となる。
  
    さて$\Omega$全体で$f$が恒等的に$0$であることを示す。
    $E_1\subset\Omega$を$f$及びその導関数が全て$0$になる点のなす集合とする。
    上で見たことより、$E_1$は開集合である。
    一方で、$E_1$は閉集合でもある。
    $\Omega$が連結で$E_1$は空でないので$\Omega=E_1$となる。  
{{< /hint >}}

上の定理の対偶で$f$が恒等的に$0$という関数でなければ、微分係数が$0$でない$k$が存在する。
このことから$f$の零点は孤立することがわかる。
特に次の事実が成り立つ。

{{< hint >}}
  $f(\alpha)=0$とし、$f(z)=\sum_{n=0}^\infty a_n(z-\alpha)^n$とおく。
  ある$n_0$で$a_{n_0}\neq0$かつ$n&lt; n_0$ならば$a_n=0$であるとする。
  このとき、
  $$
  f(z)=(z-\alpha)^{n_0}\sum_{n=0}^\infty a_{n_0+n}(z-\alpha)^n
  $$
  となる。
  $b_n=a_{n_0+n}$とおき、$g(z)=\sum_{n=0}^\infty a_{n_0+n}(z-\alpha)^n$とおく。
  $b_0\neq0$なので、$g(\alpha)=b_0\neq0$である。
  よって、ある$\epsilon$で$\lvert z-\alpha\rvert &lt;\epsilon$ならば$g(z)\neq0$となるようなものが取れる。
  この範囲においては$f(z)\neq0$でもある。
{{< /hint >}}

集積点とは。
孤立点でないこと。
$z=\alpha$が零点の集積点であるとは（$f(\alpha)\neq0$でもよい？）
任意の$\epsilon$に対してある$z\in\mathbb{C}$で$0&lt;\lvert z-\alpha\rvert&lt;\epsilon$かつ$f(z)=0$となるものが存在すること。

{{< hint >}}
    $f(z), g(z)$を領域$D$で正則な関数で、$D$内に集積点を持つ集合の上で$f(z)=g(z)$とする。
    このとき、$D$上で$f(z)=g(z)$である。  
{{< /hint >}}

{{< hint >}}
  $f-g$に対して上の定理を用いればよい。
{{< /hint >}}

{{< hint >}}
  領域$D$上の「解析関数」$f, g$があり、$D$内のある点$\alpha$において、$f(\alpha)=g(\alpha)$であるとする。
  さらに、$\alpha$のどんな近くにも（要するに集積点、収束する点列が取れる）$f(z)=g(z)$となる$z\neq\alpha$があるなら、
  $f$と$g$は$D$全体で一致する。
{{< /hint >}}

この一致の定理を用いることで、正則関数の解析接続という概念を導入する。
領域$\Omega_1$で正則な関数$f_1$と領域$\Omega_2$で正則な関数$f_2$が、共通領域$\Omega_1\cap \Omega_2$において$f_1=f_2$であるとき、$\Omega_1\cup\Omega_2$における正則関数$f$であって、$\Omega_1$上では$f_1$に一致し、$\Omega_2$上では$f_2$に一致する関数が定まる。
このような条件を満たす$f$は、一致の定理からただ一つに定まる。
これを$f_1$（あるいは$f_2$）の$\Omega_1\cup \Omega_2$への解析接続という。

上の一意性は単に$f$が連続関数であったり実関数としての$C^\infty$級という条件では成り立たない。
つまり正則関数に特有の性質であることに注意しよう。

共通部分$\Omega_1\cap\Omega_2$が連結でない場合、その複数の連結成分において同時に$f_1=f_2$が成り立つとは限らない。
このような例は後で紹介する。  

{{< hint >}}
  ベキ級数
  \begin{align*}
    f(z)=1+z+z^2+\cdots
  \end{align*}
  は$\abs{z}&lt;1$で絶対収束し正則関数を定める。

  この範囲で、等比数列の和の公式から
  \begin{align*}
    f(z)=\frac{1}{1-z}
  \end{align*}
  となる。

  この右辺の式は$z\neq1$で正則関数を定める。
{{< /hint >}}

## ガンマ関数

{{< hint >}}
  実部が$Re(s)>0$なる複素数$s$に対し
  \begin{align*}
    \int^\infty_0e^{-t}t^{s-1}dt
  \end{align*}
  をガンマ関数と呼ぶ。
  この積分は収束し、正則関数を定める。
{{< /hint >}}

部分積分により、上と同じ範囲の複素数$s$に対して
\begin{align*}
  \Gamma(s+1)=s\Gamma(s)
\end{align*}
が成り立つ。

そこで、実部が$-1$より大きな複素数$s$に対し
\begin{align*}
  G(s)=\frac{\Gamma(s+1)}{s}
\end{align*}
と定義しよう。
$s+1$の実部は$0$より大きいので、これの右辺は有理形関数で$s=0$で一位の極を持ちそれ以外では正則である。
さらに、その留数は$\Gamma(1)=1$である。

この$G(s)$について、$\Re(s)>0$においては
\begin{align*}
  G(s)=\frac{\Gamma(s+1)}{s}=\Gamma(s)
\end{align*}
が成り立つ。
つまり、$G(s)$は$\Gamma(s)$を$\Re(s)>-1$に解析接続した関数となっている。

これを繰り返すことで、$\Gamma(s)$は全複素平面に有理形関数に解析接続でき、
$s=0,-1,-2,\ldots$に$1$位の極を持つ以外では正則である。
また、極$s=-n$における留数は$\dfrac{(-1)^n}{n!}$であることがわかる。

このガンマ関数は、前に留数定理を用いて示したように
\begin{align*}
  \Gamma(s)\Gamma(1-s)=\frac{\pi}{\sin\pi s}
\end{align*}
をみたす。
