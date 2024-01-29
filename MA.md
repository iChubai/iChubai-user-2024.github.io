---
marp: true
---

## 数学分析杂题选
>
>Q3:Is $\sqrt{2}$ the limit of a sequence of numbers of the form $\sqrt[3]{n} - \sqrt[3]{m}$, where$n, m = 0, 1, 2, \cdots$
proofThe links don't work so here is a solution. Motivation: we can always make integers pop out of cube roots by placing cubes in them so if we let $m=k^3$, we want $\sqrt[3]{n} \approx k+\sqrt{2}$. Now for the proof:

For each $k\in \mathbb{N}$, let $n=\lfloor (k+\sqrt{2})^3\rfloor$ and $m=k^3$. We will apply the squeeze theorem to the sequence. Observe $\sqrt[3]{n}-\sqrt[3]{m}= \sqrt[3]{\lfloor (k+\sqrt{2})^3\rfloor} -k\\ <\sqrt[3]{(k+\sqrt{2})^3}-k\\ =\sqrt{2}.$ Further,  
$\sqrt[3]{n}-\sqrt[3]{m}= \sqrt[3]{\lfloor (k+\sqrt{2})^3\rfloor} -k\\ >\sqrt[3]{(k+\sqrt{2})^3-1}-k\\ =\frac{(k+\sqrt{2})^3-1-k^3}{\sqrt[3]{((k+\sqrt{2})^3-1)^2}+k\sqrt[3]{(k+\sqrt{2})^3-1}+k}\\ =\frac{3k^2\sqrt{2}+6k+2\sqrt{2}-1}{\sqrt[3]{((k+\sqrt{2})^3-1)^2}+k\sqrt[3]{(k+\sqrt{2})^3-1}+k}\\ =\frac{3\sqrt{2}+6\frac{1}{k}+\frac{2\sqrt{2}-1}{k^2}}{\sqrt[3]{((1+\frac{\sqrt{2}}{k})^3-\frac{1}{k^3})^2}+\sqrt[3]{(1+\frac{\sqrt{2}}{k})^3-\frac{1}{k^3}}+\frac{1}{k}}.$It is easy to see this limits to $\frac{3\sqrt{2}}{3}=\sqrt{2}$. Hence, by the squeeze theorem, the sequence $$\{\sqrt[3]{\lfloor (k+\sqrt{2})^3\rfloor}-\sqrt[3]{k^3}\}_{k=1}^\infty$$ has limit $\sqrt{2}$.
>Q4:Let $a_1,a_2,\dots$ and $b_1,b_2,\dots$ be sequences of positive real numbers such that $a_1=b_1=1$ and $b_n=b_{n-1}a_n-2$ for $n=2,3,\dots.$ Assume that the sequence $(b_j)$ is bounded. Prove that $S=\sum_{n=1}^{\infty}\frac1{a_1\cdots a_n}$converges, and evaluate $S.$

proof:Note that $a_n=\frac{b_n+2}{b_{n-1}}=\left(1+\frac2{b_n}\right)\frac{b_n}{b_{n-1}}.$ The last part telescopes in the product, giving us$a_1a_2\cdots$$a_n=\left(1+\frac2{b_2}\right)\left(1+\frac2{b_3}\right)\cdots\left(1+\frac2{b_n}\right)b_n.$
With $0<b_n\le M,$ the series for $S$ converges by comparison to a constant time a geometric series with ratio $\left(1+\frac2M\right)^{-1}.$

The sum is $\frac32.$

We claim, inductively, that for $n\ge 2,$ $S_n=\sum_{k=1}^n\frac{1}{a_1a_2\cdots a_k}=\frac32-\frac{1}{2\left(1+\frac2{b_2}\right)\cdots\left(1+\frac2{b_n}\right)}.$

For $n=2,$ $\frac32-S_2=\frac32-1-\frac{\frac1{b_2}}{1+\frac2{b_2}}=\frac1{2\left(1+\frac2{b_2}\right)},$ which starts the induction.
$\frac32-S_{n+1}=\frac32-S_n-\frac{\frac1{b_{n+1}}}{\left(1+\frac2{b_2}\right)\cdots\left(1+\frac2{b_{n+1}}\right)}\\
=\frac{1}{2\left(1+\frac2{b_2}\right)\cdots\left(1+\frac2{b_n}\right)}-\frac{\frac1{b_{n+1}}}{\left(1+\frac2{b_2}\right)\cdots\left(1+\frac2{b_{n+1}}\right)}\\
=\frac{1+\frac2{b_{n+1}}-\frac2{b_{n+1}}}{2\left(1+\frac2{b_2}\right)\cdots\left(1+\frac2{b_{n+1}}\right)}\\
=\frac{1}{2\left(1+\frac2{b_2}\right)\cdots\left(1+\frac2{b_{n+1}}\right)}$
Since $\frac32-S_n$ tends to zero, we have $S=\lim S_n=\frac32.$

> Q5:let $r_{1}$,$r_{2}$,$...$,$r_{2023}$ be the 2023 distinct roots of $x^{2023}=x+1$.Determine the value of the sum:
$\frac{r_{1}}{r_{1}^{2}+1}$+$\frac{r_{2}}{r_{2}^{2}+1}$+...+$\frac{r_{2023}}{r_{2023}^{2}+1}$

proof:Let $f(x)=x^{2023}-x-1$, then
$\sum_{n=1}^{2023}\frac{r_n}{r_n^2+1}=
\frac12\sum_{n=1}^{2023}\left(\frac1{r_n-i}+\frac1{r_n+i}\right)=
-\frac12\left(\frac{f'(i)}{f(i)}+\frac{f'(-i)}{f(-i)}\right)=
-\mathrm{Re}\left(\frac{f'(i)}{f(i)}\right)=
-\mathrm{Re}\left(\frac{-2024}{-1-2i}\right)=
-\frac{2024}{5}.$

> Q6:Suppose that $f:[0,2\pi] \rightarrow \mathbb{R}$ is a convex function. Show that for every integer $k \ge 1, \int_0^{2\pi} f\left(x\right).cos\left(kx\right)dx \ge 0.$

proof:By convexity $$f(\pi-x)\leq\frac{\pi}{2\pi-2x}f(x)+\frac{\pi-2x}{2\pi-2x}f(2\pi-x)$$ $$f(\pi+x)\leq\frac{\pi-2x}{2\pi-2x}f(x)+\frac{\pi}{2\pi-2x}f(2\pi-x)$$ which upon addition give $$f(\pi-x)+f(\pi+x)\leq f(x)+f(2\pi-x)$$ Hence $\int_0^{2\pi}f(x)\cos x\,dx=\left(\int_0^{\pi/2}+\int_{\pi/2}^\pi+\int_\pi^{3\pi/2}+\int_{3\pi/2}^{2\pi}\right)f(x)\cos x\,dx\ =\\\int_0^{\pi/2}(f(x)-f(\pi-x)-f(\pi+x)+f(2\pi-x))\cos x\,dx\geq0$ Proved !
>Q7:$\sum_{n \in \mathbb{N} }  \frac{|\sin( n)|}{n}$ 发散

$|\sin n|\geqslant \sin^2 n$, and use the convergence of $\sum_{n=1}^{+\infty}\frac{\cos(\color{red}2n)}n$ and the divergence of harmonic series.

We have $\cos(2n)=2\cos^2n-1$, and $$\sin^2n=1-\cos^2n=1-\frac{\cos(2n)+1}2=\frac{1-\cos(2n)}2.$$
>Q8:1,Let $f:[0,1]\to\mathbb{R}$ be a function such that $f\in C^1([0,1]),f(0)=f(1)=f(\frac{1}{2})=0$.Prove that \[\int_0^1 (f(x))^2dx\leq \frac{1}{32}\int_0^1 (f'(x))^2 dx\]
2,Let $f:[a,b]\to\mathbb{R}$ be a function such that $f\in C^3([a,b]),f(a)=f(b)$.Prove that $\left|\int_{a}^{\frac{a+b}{2}} f(x)dx -\int_{\frac{a+b}{2}}^{b} f(x)dx\right| \leq \frac{(b-a)^4}{192}\max_{x\in [a,b]}|f'''(x)|$

proof:1:Hint for 1: $\int_0^{1/4}f(x)^2 dx = \int_0^{1/4}\left (\int_0^x f'(t)\,dt \right )^2 dx.$
2:Write first $c = \frac{a+b}{2}$ and we can find a quadratic polynomial $P(x)$ that interpolates $\left(a,f(a)\right),\left(b,f(b)\right),\left(c,f(c)\right)$(Use Lagrange). We can find $\theta(x) \in [a,b]$ such that $f(x) = P(x) +\frac{f^{(3)}(\theta(x))}{6}.\left(x-a\right).\left(x-b\right).\left(x-c\right)$.
Further, $\int_a^c P(x)  = \frac{b-a}{24}\left(5f(a)+8f(c)-f(b)\right),\int_c^b P(x)  = \frac{b-a}{24}\left(-f(a)+8f(c)+5f(b)\right).$ Since $f(a)=f(b), \int_a^c P(x)-\int_c^b P(x) =0 $ and
$\left| \int_a^c f(x)-\int_c^b f(x) \right| = \left| \int_a^c f(x)-\int_c^b f(x) \right| = \left| \int_a^c \frac{f^{(3)}(\theta(x))}{6}.\left(x-a\right).\left(x-b\right).\left(x-c\right)-\int_c^b \frac{f^{(3)}(\theta(x))}{6}.\left(x-a\right).\left(x-b\right).\left(x-c\right) \right| \le \frac{1}{6} sup_{x \in [a,b]} |f'''(x)|.\int_a^b \left|\left(x-a\right).\left(x-b\right).\left(x-c\right)\right| = \frac{\left(b-a\right)^4}{192}.sup_{x \in [a,b]} |f'''(x)|$.
>Q9:Let $(u_{n})$ be a  sequence such that $u_1>0,u_2>0,u_{n+2}=1+\frac{u_{n+1}}{u_n},n\geq 1$.Computing $lim u_n$

proof:
$\frac{u_{n+2}}{u_{n+1}}=\frac{1}{u_{n+1}}+\frac{1}{u_{n}}$ then $u_{n+2}=1+\frac{1}{u_{n}}+\frac{1}{u_{n-1}}$
Let $(a_{n}),(b_{n})$ be: 
$a_{1}=1$, $b_{n}=1+\frac{2}{a_{n}}, a_{n+1}=1+2/b_{n}$ 
Easy to see that:
For all n, $a_{n}<u_{m}<b_{n}$ for all m full large.
Note that: $a_{n}-2=\frac{2(a_{n-1}-2)}{a_{n-1}+2}$ 
And $a_{n}>1$all n then $lim a_{n}=2$ 
Similar $lim b_{n}=2$ (?)

>Q10:Let $f$ be a real-valued function with $n+1$ derivatives at each point of $\mathbb R$. Show that for each pair of real numbers $a$, $b$, $a<b$, such that
$$\ln\left( \frac{f(b)+f'(b)+\cdots + f^{(n)} (b)}{f(a)+f'(a)+\cdots + f^{(n)}(a)}\right)=b-a$$
there is a number $c$ in the open interval $(a,b)$ for which
$$f^{(n+1)}(c)=f(c)$$

proof:Apply Rolle to the function $g(x)=(f(x)+f'(x)+\dotsc+f^{(n)}(x))e^{-x}$.

>Q11:find the limit of $$a_{n} = \frac{7^n \cdot n!}{(2+7 \cdot 1)(2 + 7 \cdot 2)...(2 + 7 \cdot n)}$$ 

proof(1):Note that $$ \frac{1}{a_n}=\frac{1}{n!}\prod_{k=1}^n\left(k+\frac{2}{7}\right)=\prod_{k=1}^n\left(1+\frac{2}{7k}\right). $$ Therefore we infer that $$ \log(1/a_n)=\sum_{k=1}^n\log\left(1+\frac{2}{7k}\right). $$ As $\log(1+x)\geq x/2$ for $x\in[0,1]$, we have $$ \log(1/a_n)\geq\sum_{k=1}^n\frac{1}{7k}, $$ and as the LHS diverges for $n\to\infty$, we infer $\log(1/a_n)\to\infty$ as $n\to\infty$. Hence $a_n\to 0$.
proof(2):Let $c$ be any strictly positive real number, such as $2/7.$ Define $$ a_n = \frac{n!}{(c+1)(c+2)\cdots(c+n)} = \prod_{k=1}^n\frac{k}{c+k} = \prod_{k=1}^n(1-b_k), $$ where $$ b_k = \frac{c}{c+k} \quad (k = 1, 2, \ldots). $$

Because $0<b_k<1$ for all $k,$ the infinite product $\prod_{k=1}^\infty(1-b_k)$ converges (to a strictly positive limit) or diverges to $0$ according as the infinite series $\sum_{k=1}^\infty b_k$ converges or diverges (to $\infty$).

(See, for example: Tom M. Apostol, Mathematical Analysis, 2nd ed. 1974, Theorem 8.55; or Peter Duren, Invitation to Classical Analysis, 2012, Chapter 5, Theorem 1.)

Because $$ b_k > \frac{c/2}{k} \quad (k > c), $$ and because $\sum_{k=1}^\infty1/k$ diverges, $\sum_{k=1}^\infty b_k$ diverges; therefore $\prod_{k=1}^\infty(1-b_k) = 0.$ That is, $\lim_{n\to\infty}a_n = 0.$

proof(3):$$\left(\frac{2}{7} + 1\right)\left(\frac{2}{7} + 2\right)\ldots\left(\frac{2}{7} + n\right)\ge n!+\frac27\sum_{i=1}^n\frac{n!}i\ge n!\left(1+\frac27\log n\right)$$

therefore

$$a_{n} = \frac{n!}{\left(\frac{2}{7} + 1\right)\left(\frac{2}{7} + 2\right)\ldots\left(\frac{2}{7} + n\right)}\le \frac{1}{1+\frac27\log n}\to 0$$

>Q12:If \(a_{n} > 0\), \(r_{n} > 0\), \(a_{n+1} = a_{n} + n \cdot r_{n}\) for \(n \in \mathbb{N}^{*}\), and \(\lim_{n \to \infty} r_{n} = r > 0\), then find  \(\Omega = \lim_{n \to \infty} \left(2H_{n} - \log a_{n}\right)\)

proof:$\Omega =\underset{n\to \infty }{\mathop{\lim }}\,\left( 2{{H}_{n}}-\log {{a}_{n}} \right)=\underset{n\to \infty }{\mathop{\lim }}\,\left( 2\left( {{H}_{n}}-\ln n \right)+\ln \frac{{{n}^{2}}}{{{a}_{n}}} \right)=2\gamma +\underset{n\to \infty }{\mathop{\lim }}\,\left( \ln \frac{{{n}^{2}}}{{{a}_{n}}} \right)$

>Q13:Compute $$\lim_{n\to\infty}\left[\frac1{\ln n}\left(\frac{\arctan1}n+\frac{\arctan2}{n-1}+\dots+\frac{\arctan(n-1)}2+\arctan n\right)\right]$$


proof:If $n$ is large we can write $\arctan n=\frac{\pi}{2}-\arctan (1/n)$
let
$$S_n=\sum_{k=0}^{n-1} \frac{\arctan (n-k)}{k+1}$$
Hence
$$S_n=\sum_{k=0}^{n-1}(\frac{\pi}{2(k+1)}-\frac{\arctan(1/(n-k))}{k+1})=\frac{\pi}{2}H_n-\sum_{k=1}^n \frac{\arctan(1/(n-k))}{k+1} $$

Now, we know that $0 \leq \arctan x \leq x$ for all $x \in [0,1]$
This led to the inequality
$$\frac{\pi}{2}H_n -\sum_{k=0}^{n-1} \frac{1}{(n-k)(k+1)} \leq S_n \leq \frac{\pi}{2}H_n$$
And note that:
$$\sum_{k=0}^{n-1} \frac{1}{(n-k)(k+1)}=\frac{1}{n+1}\sum_{k=0}^{n-1} \frac{1}{(n-k)}+\frac{1}{(k+1)}=\frac{2H_n}{n+1}$$
So
$$H_n(\frac{\pi}{2}-\frac{2}{n+1}) \leq S_n \leq  H_n \frac{\pi}{2}$$
So By squeeze theorem and the fact that $H_n/\ln n \to 1$ because I won't use the frickin $\gamma$, we conclude that $S_n/\ln n \to \frac{\pi}{2}$

Maybe it would be interesting if we get an equivalent od $S_n/\ln n-\pi/2$
>Q14:$\prod\limits_{n=0}^\infty (1+\dfrac 1{3^{3^n}})\not \in \mathbb Q$

proof:Let $C$ denote the product in question.

Firstly we prove an error bound:
[b]Lemma.[/b] $\displaystyle\prod_{n=k}^\infty\left(1+\frac{1}{3^{3^n}}\right)<\exp\left(\frac{1}{2\cdot 3^{3^k-1}}\right)$.
[i]Proof.[/i] We have $\displaystyle\prod_{n=k}^\infty\left(1+\frac{1}{3^{3^n}}\right)<\displaystyle\prod_{n=3^k}^\infty\left(1+\frac{1}{3^n}\right)$. Furthermore, $\log \displaystyle\prod_{n=3^k}^\infty\left(1+\frac{1}{3^n}\right)=\displaystyle\sum_{n=3^k}^\infty\log\left(1+\frac{1}{3^n}\right)$ which is at most $\displaystyle\sum_{n=3^k}^\infty\frac{1}{3^n}=\frac{1}{2\cdot 3^{3^k-1}}$. Quamtum Electrodynamics.

Next, we prove that the number has very good rational approximations:
[b]Lemma.[/b] There exists a constant $K$ such that there exist arbitrarily large integers $p$ and $q$ such that $(p,q)=1$ and $\left|C-\frac{p}{q}\right|<\frac{K}{q^2}$.
[i]Proof.[/i] Choose $k\ge 0$ and let $\frac{p}{q}=\displaystyle\prod_{n=0}^k\left(1+\frac{1}{3^{3^n}}\right)$ in simplified form. Then we have $\left|C-\frac{p}{q}\right|=\frac{p}{q}\left|\displaystyle\prod_{n=k+1}^\infty\left(1+\frac{1}{3^{3^n}}\right)-1\right|$. By the previous lemma, this is less than $\frac{p}{q}\left(\exp\left(\frac{1}{2\cdot 3^{3^{k+1}-1}}\right)-1\right)$ which is in turn less than $C\left(\exp\left(\frac{1}{2\cdot 3^{3^{k+1}-1}}\right)-1\right)$. As $\frac{1}{2\cdot 3^{3^{k+1}-1}}\le\frac{1}{6}$, we have $\exp\left(\frac{1}{2\cdot 3^{3^{k+1}-1}}\right)\le 1+e^{1/6}\frac{1}{2\cdot 3^{3^k-1}}$, and so putting this all together we have $\left|C-\frac{p}{q}\right|<\frac{Ce^{1/6}}{2\cdot 3^{3^{k+1}-1}}$.

Next, we note that $q=\prod_{n=0}^k 3^{3^n}=3^{\frac{3^{k+1}-1}{2}}$. Hence, we have $\left|C-\frac{p}{q}\right|<\frac{Ce^{1/6}}{2\cdot 3^{3^{k+1}-1}}=\frac{Ce^{1/6}}{2q^2}$. Since we can make $p$ and $q$ arbitrarily large by taking $k$ to be arbitrarily large, the result follows. Quantum Electrodynamics.

Finally, suppose for the sake of contradiction that $C$ was rational. Then $C$ can be written as $\frac{n}{m}$ where $n$ and $m$ are rational. Using the previous lemma, pick $p$ and $q$ such that $\left|C-\frac{p}{q}\right|<\frac{K}{q^2}$ and $q>Km$. Then we have $\frac{1}{qm}\le\left|C-\frac{p}{q}\right|<\frac{K}{q^2}<\frac{1}{qm}$, a contradiction. Therefore $C$ is irrational.

>Q15:Let $(a_n)$ be a sequence of [b]positive integers greater or equal to 2[/b]. Also, consider the sequence with the general term $$b_n=1-\frac{1}{a_1}+\frac{1}{a_1a_2}-...+(-1)^n \frac{1}{a_1a_2...a_n}$$
a) Prove that the sequence $(b_n)$ is convergent;
b) If the sequence $(a_n)$ is [b]unbounded[/b], prove that the limit of $(b_n)$ is an irrational number.

proof:Part a) follows directly from Leibnitz's criterion, but since this is not in the Olympiad curriculum, I will present instead a solution suitable for the contest.

[b]a)[/b] Notice that $|b_n| \le 1+\frac{1}{2}+\frac{1}{2^2}+\ldots+\frac{1}{2^n}<2,$ so the sequence $(b_n)$ is bounded. Now notice that the sequence $(b_{2n})$ is strictly decreasing and the sequence $(b_{2n+1})$ is strictly increasing. These sequences are therefore convergent; say their limits are $\ell_1$ and $\ell_2,$ respectively. Now notice that $|b_{n+1}-b_n|= \frac{1}{a_1a_2 \ldots a_{n+1}} \le \frac{1}{2^{n+1}},$ for any $n \ge 1.$ Taking the limit yields $|\ell_1-\ell_2|=0,$ so $\ell_1=\ell_2,$ which shows that $(b_n)$ is convergent.

[b]b)[/b] Let's assume the limit is some rational number $\frac{a}{b}.$ From the observation in the previous part, we have $b_{2n-1}<\frac{a}{b}<b_{2n},$ so $0<\frac{a}{b}-b_{2n-1}<\frac{1}{a_1a_2\ldots a_{2n}},$ for any $n>0.$ Multiplying the last relation by $ba_1a_2\ldots a_{2n-1}$ yields $0<a_1a_2 \ldots a_{2n-1}(a - bb_{2n-1})<\frac{b}{a_{2n}}.$ $(*)$ Since $(a_n)$ is unbounded, we can find some $N>0$ such that $a_{2N}>b.$ Plugging $n=N$ in $(*)$ gives us a contradiction, because the middle term is an integer.
>Q16:Let $f:\left[0,\frac{\pi}2\right]\to\mathbb{R}$ be a continuous function. Calculate $$\lim_{n\to\infty}n\int_0^{\frac{\pi}2}\left(\frac{\cos x-\sin x}{\cos x+\sin x}\right)^{2n}f(x)\,dx$$

proof:The answer is $\frac{f(0)+f(\pi/2)}{4}.$ The key is [url=https://ysharificalc.wordpress.com/2017/10/18/limit-of-integrals-6/]this fact[/url] that if $g: [0,1] \to \mathbb{R}$ is a continuous function, then 
$$\lim_{n\to\infty}n\int_0^1x^ng(x) \ dx =g(1). \ \ \ \ \ \ \ \ \ \ (*)$$
Now, write 
$$I_n:=\int_0^{\frac{\pi}2}\left(\frac{\cos x-\sin x}{\cos x+\sin x}\right)^{2n}f(x) \ dx=\int_0^{\pi/2}\left(\frac{1-\sin(2x)}{1+\sin(2x)}\right)^nf(x) \ dx=\frac{1}{2}\int_0^{\pi}\left(\frac{1-\sin x}{1+\sin x}\right)^nf(x/2) \ dx$$
$$=\frac{1}{2}\left[\int_0^{\pi/2}\left(\frac{1-\sin x}{1+\sin x}\right)^nf(x/2) \ dx + \int_{\pi/2}^{\pi}\left(\frac{1-\sin x}{1+\sin x}\right)^nf(x/2) \ dx\right].$$
So with $\frac{1-\sin x}{1+\sin x}=t,$ we get
$$I_n=\frac{1}{2}\left[\int_0^1t^nf\left(\frac{1}{2}\arcsin\left(\frac{1-t}{1+t}\right)\right)\frac{dt}{\sqrt{t}(1+t)}+\int_0^1t^nf\left(\frac{\pi}{2}-\frac{1}{2}\arcsin\left(\frac{1-t}{1+t}\right)\right)\frac{dt}{\sqrt{t}(1+t)}\right]$$
and the result follows from $(*).$

>Q17:Determinate $\lim\limits_{n\rightarrow \infty} \dfrac 1 n \sum\limits_{k=1}^n \exp(-\dfrac {k^2} n)$

proof:Let's denote $S_n=\sum_{k=1}^n e^{-\frac {k^2} n}$ and $S=\sum_{k=0}^\infty e^{-\frac {k^2} n}=S_n+1+\sum_{k=n+1}^\infty e^{-\frac {k^2} n}$
$$\Rightarrow\,\,S_n=S-1-\sum_{k=n+1}^\infty e^{-\frac {k^2} n}$$
Using the  [url=https://en.wikipedia.org/wiki/Poisson_summation_formula]Poisson' summation formula[/url]
$$S=\sum_{l=-\infty}^\infty\int_0^\infty e^{-\frac{x^2}n}e^{2\pi i lx}dx=\frac{\sqrt{\pi n}}2+\sqrt{\pi n}\sum_{l=1}^\infty e^{-\pi^2l^2n}$$
Making the estimates
$$\sum_{k=n+1}^\infty e^{-\frac {k^2} n}=\sum_{k=1}^\infty e^{-\frac {(n+k)^2} n}<\sum_{k=1}^\infty e^{-n-2k}=\frac{e^{-n}}{e^2-1}=O(e^{-n});\qquad\sum_{l=1}^\infty e^{-\pi^2l^2n}<\sum_{l=1}^\infty e^{-\pi^2l^2n}=\frac{e^{-\pi^2n}}{1-e^{-\pi^2n}}=O(e^{-\pi^2n})$$
$$S_n=\frac{\sqrt{\pi n}}2\,-\,1\,+\,O(e^{-n})+O(\sqrt n e^{-\pi^2n})\,\,\Rightarrow\,\,\boxed{\,\, \frac{S_n}n=\frac{\sqrt\pi}{2\sqrt n}\,-\,\frac1n\,+\,O\left(\frac{e^{-n}}n\right)\to 0\,\,\text{at}\,\,n\to\infty\,\,}$$

>Q18:Let $f\in C^1(a,b)$, $\lim_{x\to a^+}f(x)=\infty$, $\lim_{x\to b^-}f(x)=-\infty$ and $f'(x)+f^2(x)\geq -1$ for $x\in (a,b)$. Prove that $b-a\geq\pi$ and give an example where $b-a=\pi$.

proof:We have $f'(x)+f^2(x)\geq -1$ for $x\in (a,b).$

$$f'(x)\ge-1(1+f^2(x))\implies\frac{f'(x)}{1+f^2(x)}+1\ge0$$

Using chain rule we see that $\frac{d}{dx}\arctan f(x)=\frac{f'(x)}{1+f^2(x)}.$

And now since  $\lim_{x\to a^+}f(x)=\infty\quad\text{and}\quad\lim_{x\to b^-}f(x)=-\infty,$

We get that,

$$\int_b^a \frac{f'(x)}{1+f^2(x)}dx + \int_b^a1dx\ge0\implies\arctan f(b)-\arctan f(a)\ge a-b\implies b-a\ge\pi\quad\blacksquare$$


One such function with equality is $\cot x.$
>Q19:








