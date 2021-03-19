# VE401 Probabilistic Methods in Eng. 

## RC#3 Multi-variate Random Variable

>  By TA: DONG Juechu, Mar. 2021

if you want to edit this note, you can find it here https://github.com/joydddd/VE401-2020SP-notes

### Discrete Multivariate random variable

#### joint density function 

of the random variable $\boldsymbol{X} = \left(X_{1}, \ldots, X_{n}\right)$
$$
\text{Discrete:}\quad f_{\boldsymbol{X}}\left(x_{1}, \ldots, x_{n}\right)=P[X_1 = x_1\ and\ X_2=x_2\ ...\ and\ X_n = x_n] \\ 
\text{Continuous:}\quad P[X \in \Omega]=\int_{\Omega} f_{X}(x) d x
$$
has properties:

(i) $f_{X}(x) \geq 0$

(ii)discrete: $\sum_{x \in \Omega} f_{X}(x)=1$. continuous: $\int_{\mathbb{R}^{n}} f_{X}(x) d x=1$

#### marginal density 

$f_{X_k}$ for $X_k,\ k=1, ... ,n$
$$
\text{Discrete:}\quad f_{X_{k}}\left(x_{k}\right)=\sum_{x_{1}, \ldots, x_{k-1}, x_{k+1}, \ldots, x_{n}} f_{X}\left(x_{1}, \ldots, x_{n}\right)\\
\text{Continuous:}\quad f_{X_{k}}\left(x_{k}\right)=\int_{\mathbb{R}^{n-1}} f_{X}(x) d x_{1} \ldots d x_{k-1} d x_{k+1} \ldots d x_{n}
$$

### Bivariate Random Variable

<u>Let $\left((X, Y), f_{X Y}\right)$ be a bivariate random variable with marginal densities $f_{X}$ and $f_{Y}$.</u> 

#### Independent

$$
\text { dom } f_{X Y}=\left(\operatorname{dom} f_{X}\right) \times\left(\text { dom } f_{Y}\right) \\
f_{X Y}(x, y)=f_{X}(x) f_{Y}(y) \quad \text { for all }(x, y) \in \operatorname{dom} f_{X Y}
$$
#### conditional density 

for $X$ given $Y=y$ is
$$
f_{X \mid y}(x)=\frac{f_{X Y}(x, y)}{f_{Y}(y)}
$$
#### Expectations

Let $H: \Omega \rightarrow \mathbb{R}$ be some function. Then the expected value of $H \circ(X, Y)$ is
$$
\text{Discrete:}\quad \mathrm{E}[H \circ(X, Y)]=\sum_{(x, y) \in \Omega} H(x, y) \cdot f_{X Y}(x, y)\\
\text{Continuous:}\quad \mathrm{E}[H \circ(X, Y)]=\iint_{\mathbb{R}^{2}} H(x, y) \cdot f_{X Y}(x, y) d x d y
$$
specially consider $H(x, y)=x$ and $H(x, y)=y,$ giving
$$
\text{Discrete:}\\
\mathrm{E}[X]=\sum_{(x, y) \in \Omega} x \cdot f_{X Y}(x, y), \quad \mathrm{E}[Y]=\sum_{(x, y) \in \Omega} y \cdot f_{X Y}(x, y) \\
\text{Continuous:}\\
\mathrm{E}[X]=\iint_{\mathbb{R}^{2}} x \cdot f_{X Y}(x, y) d x d y, \quad \mathrm{E}[Y]=\iint_{\mathbb{R}^{2}} y \cdot f_{X Y}(x, y) d x d y
$$
#### ==Conditional Expectations==

$$
\text{Discrete:}\\
\mathrm{E}[Y \mid x]:=\sum_{y} y \cdot f_{Y \mid x}(y), \quad \mathrm{E}[X \mid y]:=\sum_{x} x \cdot f_{X \mid y}(x) \\
\text{Continuous:}\\
\mathrm{E}[Y \mid x]:=\int_{\mathbb{R}} y \cdot f_{Y \mid x}(y) d y, \quad \mathrm{E}[X \mid y]:=\int_{\mathbb{R}} x \cdot f_{X \mid y}(x) d xdsdf
$$
### ==Transformation of Variables==

Let $\left(X, f_{X}\right)$ be a continuous multivariate random variable and let $\varphi: \mathbb{R}^{n} \rightarrow \mathbb{R}^{n}$ be a differentiable, bijective map with inverse $\varphi^{-1}$. Then $Y=\varphi \circ X$ is a continuous multivariate random variable with density
$$
f_{Y}(y)=f_{X} \circ \varphi^{-1}(y) \cdot\left|\operatorname{det} D \varphi^{-1}(y)\right|
$$
where $D \varphi^{-1}$ is the Jacobian of $\varphi^{-1}$.

Let $\left((X, Y), f_{X Y}\right)$ be a continuous bivariate random variable. Let $U=X / Y$. Then the density $f_{U}$ of $U$ is given by
$$
f_{U}(u)=\int_{-\infty}^{\infty} f_{X Y}(u v, v) \cdot|v| d v
$$

> ### Sum of Two Continuous Random Variables
>
> Sum of Two Continuous Random Variables Let $X$ and $Y$ be continuous random variables with parameters with joint density $f_{X Y} .$ Let $U=X+Y$ and prove that the density of $U$ is given by
> $$
> f_{U}(u)=\int_{-\infty}^{\infty} f_{X Y}(u-v, v) d v
> $$
> Hint: Consider the transformation $(x, y) \mapsto(x+y, y)$. 

> ### Sum of Two Exponential Distributions
>
> Let $X$ and $Y$ be independent exponentially distributed random variables with parameters $\beta_{1}=1 / 3$ and $\beta_{2}=1$ respectively. Let $U=X+Y$ and show that
> $$
> f_{U}(u)=\left\{\begin{array}{ll}
> \left(e^{-u / 3}-e^{-u}\right) / 2 & u>0 \\
> 0 & u \leq 0
> \end{array}\right.
> $$



### Covariance

$$
\begin{array}{r}
\operatorname{Cov}[X, Y]=E\left[\left(X-\mu_{X}\right)\left(Y-\mu_{Y}\right)\right] \\
\operatorname{Cov}[X, Y]=E[X Y]-E[X] E[Y]
\end{array}
$$
- $\operatorname{Cov}[X, X]=\operatorname{Var}[X]$.

- If $X$ and $Y$ are independent, then $\operatorname{Cov}[X, Y]=0$.

#### covariance matrix

$$
\operatorname{Var}[X]=\left(\begin{array}{cccc}
\operatorname{Var}\left[X_{1}\right] & \operatorname{Cov}\left[X_{1}, X_{2}\right] & \ldots & \operatorname{Cov}\left[X_{1}, X_{n}\right] \\
\operatorname{Cov}\left[X_{1}, X_{2}\right] & \operatorname{Var}\left[X_{2}\right] & \ddots & \vdots \\
\vdots & \ddots & \ddots & \operatorname{Cov}\left[X_{n-1}, X_{n}\right] \\
\operatorname{Cov}\left[X_{1}, X_{n}\right] & \ldots & \operatorname{Cov}\left[X_{n-1}, X_{n}\right] & \operatorname{Var}\left[X_{n}\right]
\end{array}\right)
$$
for constant $n \times n$ matrix with real coefficients $C \in \operatorname{Mat}(n \times n ; \mathbb{R})$
$$
\operatorname{Var}[C X]=C \operatorname{Var}[X] C^{\top}
$$
#### Standardized Random Variable

$$
\tilde{X}:=\frac{X-\mu_{X}}{\sigma_{X}}
$$
$$
\mathrm{E}[\tilde{X}]=0, \quad \operatorname{Var}[\tilde{X}]=1
$$

#### Pearson coefficient

 of correlation of (X, Y)
$$
\rho_{X Y}:=\frac{\operatorname{Cov}[X, Y]}{\sqrt{\operatorname{Var}[X] \operatorname{Var}[Y]}} =\operatorname{Cov}\left[\tilde{X}, \tilde{Y}\right]
$$

- $-1 \leq \rho_{X Y} \leq 1$
-  $\left|\rho_{X Y}\right|=1$ if and only if there exist numbers $\beta_{0}, \beta_{1} \in \mathbb{R}, \beta_{1} \neq 0,$ such that $Y=\beta_{0}+\beta_{1} X$ almost surely.

### Linearity of X and Y

#### ==Fisher Transformation==

$$
\rho_{X Y}=\tanh \left(\ln \left(\frac{\sigma_{\tilde{X}}+\tilde{Y}}{\sigma_{\tilde{X}-\tilde{Y}}}\right)\right)
$$
- If $\rho_{X Y}>0,$  $X$ and $Y$ are positively correlated.
- If $\rho_{X Y}<0,$  $X$ and $Y$ are negatively correlated.

#### ==Bivariate normal distribution==

$$
\begin{array}{l}
f_{X Y}(x, y)=\frac{1}{2 \pi \sigma_{X} \sigma_{Y} \sqrt{1-\varrho^{2}}} e^{-\frac{1}{2\left(1-\varrho^{2}\right)}\left[\left(\frac{x-\mu_{X}}{\sigma_{X}}\right)^{2}-2 \varrho\left(\frac{x-\mu_{X}}{\sigma_{X}}\right)\left(\frac{y-\mu_{Y}}{\sigma_{Y}}\right)+\left(\frac{y-\mu_{Y}}{\sigma_{Y}}\right)^{2}\right]} \\
\text { where }-1<\varrho<1
\end{array}
$$

> ### Covariant and Bivariate normal distribution
>
> Let $X=\left(X_{1}, X_{2}\right)$ be a random vector. Then we define the expectation vector and the variance-covariance matrix as follows:
> $$
> \mathrm{E}[X]:=\left(\begin{array}{c}
> \mathrm{E}\left[X_{1}\right] \\
> \mathrm{E}\left[X_{2}\right]
> \end{array}\right), \quad \operatorname{Var} X:=\left(\begin{array}{cc}
> \operatorname{Var} X_{1} & \operatorname{Cov}\left(X_{1}, X_{2}\right) \\
> \operatorname{Cov}\left(X_{2}, X_{1}\right) & \operatorname{Var} X_{2}
> \end{array}\right)
> $$
> Let $A$ be a constant $2 \times 2$ matrix and $Y=\left(Y_{1}, Y_{2}\right)=A X$.
>
> 1. Show that $\mathrm{E}[A X]=A \mathrm{E}[X]$. 
> 2. Show that $\operatorname{Var}(A X)=A(\operatorname{Var} X) A^{T}$.
> 3. Suppose that $X_{1}$ and $X_{2}$ follow independent normal distributions with means $\mu_{1}$ and $\mu_{2}$ and variances $\sigma_{1}^{2}$ and $\sigma_{2}^{2}$, respectively. Show that the joint density is given by
>
> $$
> f_{X}(x)=f_{X}\left(x_{1}, x_{2}\right)=\frac{1}{2 \pi \sqrt{\operatorname{det} \Sigma_{X}}} e^{-\frac{1}{2}\left\langle x-\mu_{X}, \Sigma_{X}^{-1}\left(x-\mu_{X}\right)\right\rangle}
> $$
> where $\mu_{X}=\left(\mu_{1}, \mu_{2}\right)$ and $\Sigma_{X}=\operatorname{diag}\left(\sigma_{1}^{2}, \sigma_{2}^{2}\right)$ is the $2 \times 2$ matrix with the variances on the diagonal and all other entries vanishing. (1 Mark)
> iv) Suppose that $X_{1}$ and $X_{2}$ follow independent normal distributions with means $\mu_{1}, \mu_{2} \in \mathbb{R}$ and variances $\sigma_{1}^{2}, \sigma_{2}^{2}>0,$ respectively. Let $Y=A X$ where $A$ is an invertible $n \times n$ matrix. Show that
> $$
> f_{Y}(y)=\frac{1}{2 \pi \sqrt{\left|\operatorname{det} \Sigma_{Y}\right|}} e^{-\frac{1}{2}\left\langle y-\mu_{Y}, \Sigma_{Y}^{-1}\left(y-\mu_{Y}\right)\right\rangle}
> $$
> where $\mu_{Y}=\mathrm{E}[Y], \Sigma_{Y}=\operatorname{Var} Y$ and $\langle\cdot, \cdot\rangle$ denotes the euclidean scalar product in $\mathbb{R}^{2}$.
> v) Show that $(*)$ can be written as
> $$
> f_{Y}\left(y_{1}, y_{2}\right)=\frac{1}{2 \pi \sigma_{Y_{1}} \sigma_{Y_{2}} \sqrt{1-\varrho^{2}}} e^{-\frac{1}{2\left(1-\varrho^{2}\right)}}\left[\left(\frac{y_{1}-\mu_{Y_{1}}}{\sigma_{Y_{1}}}\right)^{2}-2 \varrho\left(\frac{y_{1}-\mu_{Y_{1}}}{\sigma_{Y_{1}}}\right)\left(\frac{y_{2}-\mu_{Y_{2}}}{\sigma_{Y_{2}}}\right)+\left(\frac{y_{2}-\mu_{Y_{2}}}{\sigma_{Y_{2}}}\right)^{2}\right]
> $$
> where $\mu_{Y_{i}}$ is the mean and $\sigma_{Y_{i}}^{2}$ the variance of $Y_{i}, i=1,2,$ and $\varrho$ is the correllation of $Y_{1}$ and $Y_{2}$. 

