## Transform Methods

`transform methods` are used to compute moments of a RV $X$:

$$
\Bbb{E}[x^k] \text{ where }k\ge 1
$$

They are also used to compute sums of independent RVs

## Characteristic Function

$$
\Phi_x(\omega) = \Bbb{E}[e^{j\omega x}]\text{ where } j=\sqrt{-1}
$$

Consider $x$ ~ exponential($\lambda$)

$$
\begin{align*}
\Phi_x(\omega) &= \int_0^{\infty}e^{j\omega x}\lambda e^{-\lambda x}dx \\
&= \int_0^{\infty}\lambda e^{-(\lambda - j\omega) x}dx \\
& = \frac{\lambda}{\lambda - j\omega}
\end{align*}
$$

Finding moments of $x$ based on $\Phi_x(\omega)$

Recall, the Taylor Series Expansion of $e^x = 1 + \frac{x}{1!} + \frac{x^2}{2!} + \frac{x^3}{3!} + ...$

$$
\begin{align*}
\Phi_x(\omega) &= \int_{-\infty}^{\infty}e^{j\omega x}f_X(x)dx \\
&= \int_{-\infty}^{\infty}f_X(x)[1 + \frac{j\omega x}{1!} + \frac{(j\omega x)^2}{2!} + \frac{(j\omega x)^2}{3!} + ...]dx \\
&= \int_{-\infty}^{\infty}f_X(x)\sum_{k=0}^\infty\frac{(j\omega x)^k}{k!}dx \\
&= \sum_{k=0}^\infty \int_{-\infty}^{\infty}\frac{(j\omega x)^k}{k!} f_X(x)dx \\
&= \sum_{k=0}^\infty \frac{(j\omega)^k}{k!} \int_{-\infty}^{\infty} x^k f_X(x)dx \\
&= \sum_{k=0}^\infty \frac{(j\omega)^k}{k!} \Bbb{E}[x^k]
\end{align*}
$$

Characteristic function $\Phi_x(\omega)$ is a scaled sum of moments of $X$

Let's take the derivative $\frac{d}{d\omega}\Phi_x(\omega)$

$$
\begin{align*}
\frac{d}{d\omega}\Phi_x(\omega) &= \frac{d}{d\omega}[1 + \frac{j\omega}{1!}\Bbb{E}[x] + \frac{(j\omega)^2}{2!}\Bbb{E}[x^2] + \frac{(j\omega)^3}{3!}\Bbb{E}[x^3] + ...] \\
&= 0 + \frac{j}{1!}\Bbb{E}[x] + \frac{2j^2\omega}{2!}\Bbb{E}[x^2] + \frac{3j^3\omega^2}{3!}\Bbb{E}[x^3] + ...
\end{align*}
$$

$$
\frac{d}{d\omega}\Phi_x(\omega) |_{\omega = 0} = \frac{j}{1!}\Bbb{E}[x]
$$

The first moment of x is equal to:

$$
\Bbb{E}[x] = \frac{1}{j}(\frac{d}{d\omega}\Phi_x(\omega) |_{\omega = 0})
$$

Let's do the second derivative of the characteristic function:

$$
\begin{align*}
\frac{d^2}{d\omega^2}\Phi_x(\omega) &= \frac{d}{d\omega}[\frac{j}{1!}\Bbb{E}[x] + \frac{2j^2\omega}{2!}\Bbb{E}[x^2] + \frac{3j^3\omega^2}{3!}\Bbb{E}[x^3] + ...] \\
&= \frac{j^2}{1!}\Bbb{E}[x^2] + \frac{2j^3\omega}{2!}\Bbb{E}[x^3] ...
\end{align*}
$$

$$
\frac{d^2}{d\omega^2}\Phi_x(\omega) |_{\omega = 0} = \frac{j^2}{1!}\Bbb{E}[x^2] = \Bbb{E}[x^2]
$$

The second moment of x is equal to:

$$
\Bbb{E}[x^2] = \frac{1}{j^2}(\frac{d^2}{d\omega^2}\Phi_x(\omega) |_{\omega = 0})
$$

In general:

$$
\Bbb{E}[x^k] = \frac{1}{j^k}(\frac{d^k}{d\omega^k}\Phi_x(\omega) |_{\omega = 0})
$$

Examples:

Earlier we found $\Phi_x(\omega) = \frac{\lambda}{\lambda - j\omega}$

$$
\frac{d}{d\omega}\Phi_x(\omega) = \frac{\lambda j}{(\lambda - j\omega)^2}
$$

$$
\frac{d}{d\omega}\Phi_x(\omega)|_{\omega = 0} = \frac{\lambda j}{\lambda^2} = \frac{j}{\lambda}
$$

$$
\Bbb{E}[x]= \frac{1}{j}\frac{j}{\lambda} = \frac{1}{\lambda}
$$

$$
\frac{d^2}{d\omega^2}\Phi_x(\omega) = \frac{2\lambda j^2}{(\lambda - j\omega)^3}
$$


$$
\frac{d^2}{d\omega^2}\Phi_x(\omega)|_{\omega = 0} = \frac{2\lambda j^2}{\lambda^3} = \frac{2j^2}{\lambda^2}
$$

$$
\Bbb{E}[x^2]= \frac{1}{j^2}\frac{-2}{\lambda^2} = \frac{2}{\lambda^2}
$$

Let's consider a sum of independent RVs $Y = \sum_{i=1}^nx_i$

$$
\begin{align*}
\Phi_Y(\omega) = \Bbb{E}[e^{j\omega Y}] &= \Bbb{E}[e^{j\omega (x_1 + x_2 + x_3 + ...)}] \\
&= \Bbb{E}[e^{j\omega x_1}e^{j\omega x_2}e^{j\omega x_3}...]\\
&= \Bbb{E}[e^{j\omega x_1}]\Bbb{E}[e^{j\omega x_2}]\Bbb{E}[e^{j\omega x_3}]...
\end{align*}
$$

Let's now consider a special case where $x_i, 1\le i \le n$ are independent and identically distributed `i.i.d`

$$
\begin{align*}
\Phi_Y(\omega) &= \Bbb{E}[e^{j\omega x_1}]\Bbb{E}[e^{j\omega x_2}]\Bbb{E}[e^{j\omega x_3}]...\\
&= [\Phi_x(\omega)]^n
\end{align*}
$$

Consider the following:

$z=x+y$ and $X, Y$ are continuous and independent

$$
\begin{align*}
\Phi_z(\omega) &= \Bbb{E}[e^{j\omega z}]\\
&= \Bbb{E}[e^{j\omega (x+y)}] \\
&= \Bbb{E}[e^{j\omega x}e^{j\omega y}] \\
&= \Bbb{E}[e^{j\omega x}] \Bbb{E}[e^{j\omega y}] \\
&= \Phi_x(\omega) \Phi_y(\omega)
\end{align*}
$$

$$
f_Z(z) = f_X(x)f_Y(y)
$$

In addition to $\Phi_x(\omega)$ there are also the following:

* moment generating function $\Bbb{E}[e^{tx}]|_{t=jw}=\Phi_x(\omega)$
* probability generating function: applies when x is integer value and non-negative
    * $G_x(z) = \Bbb{E}[z^X] = \sum_{k=0}^{\infty}P(X=k)z^k$ where $X$ is an RV and $z$ is a parameter

$$
\begin{align*}
G_X(z) &= \sum_{k=0}^{\infty}(1-p)^{k-1}pz^k \\
&= zp\sum_{k=0}^{\infty}(1-p)^{k-1}z^k-1 \\
&= zp\frac{1}{1-(1-p)z}
\end{align*}
$$

$$
G_X(z)|_{z=1} = 1
$$

$$
\frac{d}{dx}G_X(z)|_{z=1} = \sum_{k=0}^{\infty} P(X=k)kz^{k-1}|_{z=1} = \Bbb{E}[x]
$$
