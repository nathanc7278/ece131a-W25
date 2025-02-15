# Functions of RV $Y = g(x)$

Let $X$ be a RV and let $Y$ be another RV that results from applying $g$ to $X$.

Consider the following:

1. $X$ is discrete, $Y$ is also discrete
1. $X$ is continuous, $Y$ is also discrete
1. $X$ is continuous, $Y$ is also continuous
1. $X$ is discrete, $Y$ is also ccontinuous

In general we want to express $P(Y \in c) = P(g(x) \in c) = P(X \in B)$ where $B$ is the set of values of $X$ for which $g(x)$ is contained in $c$.

## $X$ is discrete, $Y$ is also discrete

Procedure: to find the probability that $Y=y$, collect all values of $X=x$, such that $g(x)=y$ and add up their probabilities.

Let 

$$
B_Y= \{ x: g(x) = y \}
$$

$$
P(Y=y) = \sum P(X=x)
$$

Example: Suppose there are $N$ sensors in a sensor network. Each sensor sends a signal to the fusion center with probability $p$ independently of other sensors. The network can sustain up to $M$ concurrent signals. When there are more than $M$ signals, $X-M$ of them are discarded at random. $X$ denotes the number of sensors sending signals. Compute the PMF of the number of discarded signals.

Each sensor can be modelled as a Bernoulli RV ($p$)

$X$ is a Binomial RV ($N,p$)

$P(X,x) = {N\choose x}p^x(1-p)^{N-x}$

$$
Y = \begin{cases}
0, X-M \le 0 \\
X-M, X-M \gt 0
\end{cases}
$$

$$
Y=(X-M)^+
$$

$$
h(x)^+ = \begin{cases}
0, h(x) \le 0 \\
h(x), h(x) \gt 0
\end{cases}
$$

$$
X \in \{0, 1, ..., N-1, N\}
$$

$$
P(Y=0) \text{ when } (X-M)^+ = 0
$$

$$
Y=0 \text{ when } x\in \{0, 1, 2, ..., M\}
$$

$$
\begin{align*}
P(Y=0) &= P(X\in \{0, 1, 2, ..., M\})\\
&= \sum_{k=0}^M{N\choose k}p^k(1-p)^{N-k}
\end{align*}
$$

$$
\begin{align*}
P(Y=1) &= P(X = M+1) \\
&={N\choose M+1}p^{M+1}(1-p)^{N-(M+1)}
\end{align*}
$$

$$
\begin{align*}
P(Y=2) &= P(X = M+2) \\
&={N\choose M+2}p^{M+2}(1-p)^{N-(M+2)}
\end{align*}
$$

Therefore:

$$
\begin{align*}
P(Y=k) &= P(X = M+k) \\
&={N\choose M+k}p^{M+1}(1-p)^{N-(M+k)}
\end{align*}\\
\text{ for } 1 \le k \le N-M
$$

## $X$ is continuous, $Y$ is also discrete

Procedure: To find the probability of $Y=y$, we collect all intervals of $X$ where $g(X)=y$ and add up their probabilities.

Let $B_Y= \{x: g(x) = y\}$

$P(Y=y) = \int f_X(x)dx$

Example: Quantization

Let $X$ be an exponential RV with parameter $\lambda$. Let $Y$ be a quantized version of $X$ such that $Y= \text{floor} (X)$

Compute the PMF of $Y$

$Y \in \{0, 1, 2, ... \}$

$$
\begin{align*}
P(Y=0) &= \int_0^1 f_X(x)dx\\
&= \int_0^1 \lambda e^{-\lambda x}dx\\
&= 1- e^{-\lambda}
\end{align*}
$$

$$
\begin{align*}
P(Y=k) &= \int_k^{k+1} \lambda e^{-\lambda x}dx\\
&= e^{-\lambda k}-e^{-\lambda (k+1)}\\
\text{when } k\in N
\end{align*}
$$

## $X$ is continuous, $Y$ is also continuous

Procedure: Express CDF of $Y, F_Y$ in terms of the CDF of $X, F_X$. Evaluate $F_Y$ at appropiate values. Differentiate to get $f_Y(y)$, the PDF of $Y$.

Example: Linear Transformation

$Y = aX + b$ when $a \ne 0$

Suppose $X$ is continuous with CDF $F_X$

$$
\begin{align*}
F_Y(y) &= P(Y \le y)\\
&= P(aX+b \le y)\\
&= P(x \le \frac{y-b}{a}) \text{ when }  a > 0 
\end{align*}
$$

$$
F_Y(y) = \begin{cases}
F_X(\frac{y-b}{a}) \text{ when } a > 0\\
1-F_X(\frac{y-b}{a}) \text{ when } a <> 0
\end{cases}
$$

Next we compute $f_X(x)$ by differentiation.

For $a>0$: (use chain rule)

$$
\begin{align*}
f_Y(y) &= \frac{d}{dy}F_Y(y)\\
&=  \frac{d}{dy}F_X(\frac{y-b}{a})\\
&= f_X(\frac{y-b}{a})\frac{1}{a}
\end{align*}
$$

Now for $a<0$:

$$
\begin{align*}
f_Y(y) &= \frac{d}{dy}F_Y(y)\\
&=  \frac{d}{dy}(1-F_X(\frac{y-b}{a}))\\
&= -f_X(\frac{y-b}{a})\frac{1}{a}
\end{align*}
$$

Therefore:

$$
F_Y(y)= \frac{1}{|a|} F_X(\frac{y-b}{a})
$$

Example: $Y=x^2$ Find the PDF of $Y$ in terms of PDF of $X$ when $X$ is continuous.

$$
\begin{align*}
F_Y(y) = P(Y\le y) &= P(x^2 \le y) \text{ when } y\ge 0\\
&= P(-\sqrt{y} \le X \le \sqrt{y})\\
&= F_X(\sqrt{y}) - F_X(-\sqrt{y})
\end{align*}
$$

$$
\begin{align*}
f_Y(y) &= \frac{d}{dy}F_Y(y)\\
&= \frac{d}{dy}[F_X(\sqrt{y})-F_X(-\sqrt{y}))]\\
&= f_X(\sqrt{y})\frac{1}{2\sqrt{y}} - f_X(-\sqrt{y})(-\frac{1}{2\sqrt{y}})\\
&= \frac{1}{2\sqrt{y}}[f_X(\sqrt{y}) + f_X(-\sqrt{y})]
\end{align*}
$$

Example: $Y= X^2$ and $X$ is a standard gaussian $N(0,1)$

$$
P(Y \le y) = P(X^2 \le y)
$$

Recall: $f_X(a)= \frac{1}{\sqrt{2\pi}}e^{-\frac{a^2}{2}}$

$$
\begin{align*}
f_Y(y)&= \frac{1}{2\sqrt{y}}[\frac{1}{\sqrt{2\pi}}e^{-\frac{y^2}{2}} + \frac{1}{\sqrt{2\pi}}e^{-\frac{y^2}{2}})] \\
&=\frac{2}{2\sqrt{2\pi y}}e^{-\frac{y}{2}} \text{ when } y\ge 0
\end{align*}
$$
