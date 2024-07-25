---
title: "Liouville Theorem"
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
<title>リュービルの定理</title>
</head>
<body>
<h1>リュービルの定理</h1>


    リューヴィルの定理．最大値の原理
    コーシーの積分公式の応用として，リューヴィルの定理，代数学の基本定理，最大値の原理などについて解説する．    
    コーシーの積分公式を用いて次のリュービルの定理を証明し、
    その応用として任意の多項式は必ず複素数の範囲で解を持つという事実を証明しよう。



    リューヴィルの定理とは。
    $\CC$上正則で有界な関数は定数のみ。


{{< hint >}}
    複素平面$\CC$全体で正則な関数$f$に対し、
    ある定数$M$が存在して任意の$z\in\CC$に対して$\abs{f(z)}&lt;M$であるとする。
    このとき、$f$は定数関数である。
{{< /hint >}}

{{< hint >}}
    $f(z)$を有界と仮定し、その上界を一つとり$M$とする。
    つまり、任意の$z\in\CC$に対し$\abs{f(z)}&lt;M$である。
  
    先ほど示したことから任意の円周$C$に対し、その内部の点$z$について
    \begin{align*}
      f'(z)=\frac{1}{2\pi i}\int_C\frac{f(\zeta)}{(\zeta-z)^2}d\zeta
    \end{align*}
    である。
  
    $C$を半径$r$で中心$z=a$の円周とすると
    \begin{align*}
      \abs{f'(a)}&\leq\frac{1}{2\pi i}\int_C\frac{\abs{f(\zeta)}}{(\zeta-a)^2}\abs{d\zeta}\\
      &\leq Mr^{-2}
    \end{align*}
    であるが、これが任意の$r$で成立するから$f'(a)=0$である。
  
    よって任意の$z\in\CC$で$f'(z)=0$となり$f(z)$は定数関数である。  
{{< /hint >}}


    代数学の基本定理


{{< hint >}}
    $1$次以上の複素数係数多項式は複素数の範囲に解を持つ。
{{< /hint >}}

{{< hint >}}
    $P(z)$を$1$次以上の多項式とし、解を持たないと仮定する。
    $z\to\infty$で$\abs{P(z)}\to\infty$であることから、
    $\dfrac{1}{P(z)}$は$\CC$上で有界になる。
    リュービルの定理より$P(z)$は定数となり、これは矛盾。  
{{< /hint >}}


    最大値の原理


{{< hint >}}
    $f:D\to\CC$が正則で定数でないなら、$f$の絶対値は最大値を持たない。
{{< /hint >}}

{{< hint >}}
    $\alpha\in D$で絶対値が最大とする。
    任意の$z$について$\lvert f(z)\rvert\leq\lvert f(\alpha)\rvert$である。
    このとき、コーシーの積分公式から、
    $$
    \lvert f(\alpha)\rvert=\lvert\frac{1}{2\pi i}\int_C\frac{f(z)}{z-\alpha}dz\rvert\\
    \leq\frac{1}{2\pi}\frac{\lvert f(\alpha)\rvert}{r}2\pi r=\lvert f(\alpha)\rvert
    $$
    となるため、$C$上で$\lvert f(z)\rvert=\lvert f(\alpha)$となる。
    $C$は任意に取れるから、$\lvert f(z)\rvert$は一定である。

    $f=u+iv$とすると、$u^2+v^2$が定数で、これを$x, y$でそれぞれ変微分すると、
    $2u_xu+2v_xv=0, 2u_yu+2v_yv=0$となり、コーシーリーマン方程式より$-2v_xu+2u_xv=0$となるから、
    $u_x=v_x=u_y=v_y=0$となる。
    よって$f$は定数。
{{< /hint >}}


    平均値の性質


{{< hint >}}
    $f$が円$C=C(\alpha,r)$とその内部で正則であるとき、
    $$
    f(\alpha)=\frac{1}{2\pi}\int^{2\pi}_0f(\alpha+re^{i\theta})d\theta
    $$
    である。
{{< /hint >}}

{{< hint >}}
    コーシーの積分公式を使って、$z=\alpha+re^{i\theta}$と置換する。
    $$
    f(\alpha)=\frac{1}{2\pi i}\int_C\frac{f(z)}{z-\alpha}dz\\
    =\frac{1}{2\pi i}\int^{2\pi}_0\frac{f(\alpha+re^{i\theta})}{re^{i\theta}}ire^{i\theta}d\theta\\
    =\frac{1}{2\pi}\int^{2\pi}_0f(\alpha+re^{i\theta})d\theta\\
    $$
    である。
{{< /hint >}}

</body>
</html>