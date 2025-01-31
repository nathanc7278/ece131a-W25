All probabilities of interest associated witha  given random variable `X` can be expressed in terms of a CDF

1. $P(a\lt X \le b) = F_X(b) - F_X(a)$
2. $P(X = b) = F_X(b) - F_X(b^-)$
3. $P(x \gt a) = 1- F_X(a)$
4. $P(a\le X \le b) = F_X(b) - F_X(a^-)$
5. $P(a \lt X \lt b) = -F_X(a) + F_X(b^-)$

## Continuous RV

There are no jumps in the CDF. So $\forall a \in \Bbb{R} P(X=a) = 0$. Therefore PMF provides no information.

## Probabilty Density Function(PDF)

$$f_X = \frac{d}{dx}F_X(x)$$

$$
\begin{align*}
P(x \lt X \in x+h) &= \frac{F(x+h)-F_X(x)h}{h}\\
&= f_X(x)h 
\end{align*}
$$

From this equation we know that the probability is equal to the density times the height.

### Properties of PDF

1. $f_X(x) \ge 0$
2. $\int_{-\infty}^{x}f_X(t)dt = F_X(x)$
3. $P(a \le x \le b)$ for continuous RV = $\int_{a}^{b}f_X(t)dt$
4. $\int_{-\infty}^{\infty}f_X(t)dt = 1$

Examples: uniform continuous RV: x ~ uniform[a,b]

![uniformrv1](./Images/uniformrv1.jpg)

$$
\begin{align*}
\int_{-\infty}^{\infty}f_X(t)dt &= 1\\
\int_{a}^{b}cdt &= 1\\
c(b-a) &=1\\
c &= \frac{1}{b-a}
\end{align*}
$$

![uniformrv1](./Images/uniformrv2.jpg)

Describing uniform continuous RV ~ uniform[a,b]

$$
f_X(x) = 
\begin{cases}
   \frac{1}{b-a} & a \le x \le b\\
   0 & \text{otherwise}
\end{cases}
$$

$$
F_X(x) = 
\begin{cases}
   0 & x \lt a \\
   \frac{x-a}{b-a} & a \le x \le b\\
   1 & x \gt b
\end{cases}
$$

The expectation of a continuous RV is:

$$
\Bbb{E}[g(x)] = \int_{-\infty}^{\infty}g(x)f_X(x)dx
$$

Example: Compute the expectation for x~uniform[a,b]

$$
\begin{align*}
\Bbb{E}[x] &= \int_{a}^{b}x\frac{1}{b-a}dx\\
&=\frac{b^2-a^2}{2(b-a)}\\
&=\frac{a+b}{2}
\end{align*}
$$

$$
\begin{align*}
\text{VAR}(X) = \Bbb{E}[(X-m_X)^2] = \Bbb{E}[X^2] - m_X^2\\
\Bbb{E}[X^2] &= \int_{a}^{b}x^2\frac{1}{b-a}dx\\
&= \frac{b^3-a^3}{3(b-a)}\\
\text{VAR}(X) = \frac{b^3-a^3}{3(b-a)} - (\frac{a+b}{2})^2
\end{align*}
$$

Example:

$$
f_X(x) = 
\begin{cases}
   cx & 0 \le x \le 2\\
   0 & \text{otherwise}
\end{cases}
$$

* Find constant $c$
* Find the CDF of $X$
* Compute $P(X\lt 1)$

$$
\begin{align*}
\int_0^2cxdx &= 1\\
[\frac{cx^2}{2}]_0^2 &= 1\\
2c &= 1\\
c &= \frac{1}{2}
\end{align*}
$$

CDF of $X = F_X(x)$

$$
F_X(x) \text{ for } 0 \le x \le 2
$$

$$
\begin{align*}
&= \int_{-\infty}^xf_X(t)dt \\
&= \int_0^x\frac{1}{2}tdt \\
&= [\frac{t^2}{4}]_0^x\\
&= \frac{x^2}{4}
\end{align*}
$$

$$
F_X(x) =
\begin{cases}
    0 & x \lt 0\\
    \frac{x^2}{4} & 0\le x \le 2\\
    1 & x\gt 2
\end{cases}
$$

$$
F_X(1) = \frac{1}{4}
$$

## Exponential RV($\lambda$)

$\lambda \gt 0$

$$
P(X \gt a) = e^{-\lambda a} \text{ where } x\gt 0, a\gt 0
$$

$$
F_X(a) = 1-e^{-\lambda a}
$$

$$
f_X(a) = \lambda e^{-\lambda a} \gt 0
$$

### Memoryless Property:

We say that RV X is mermoryless if:

$$
P(X \gt t+h | x \gt t) = P(X \gt h)
$$

$$
\frac{P(X \gt t+h , x \gt t)}{P(X \gt t)} = \frac{P(X \gt t+h)}{P(X \gt t)}
$$

because $t+h$ happens after $t$.

Specifically for x~exp($\lambda$):

$$
P(x\gt t+h | x \gt t)\frac{P(X \gt t+h)}{P(X \gt t)} = \frac{e^{-\lambda (t+h)}}{e^{-\lambda t}} = e^{-\lambda h} = P(x \gt h)
$$

$$
\Bbb{E}[x] = \int_0^\infty x\lambda e^{-\lambda x}dx = \frac{1}{\lambda}
$$

$$
\text{VAR}(x) = \Bbb{E}[x^2] - \frac{1}{\lambda ^2} = \frac{1}{\lambda ^2}
$$

## Gaussian RV x~N($\mu, \sigma ^2$)

$$
f_X(x) = \frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(x-\mu)^2}{2\sigma^2}} \text{ for } x \in \Bbb{R}, f_X(X)\gt 0
$$
