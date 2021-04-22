# VE401 Probabilistic Methods in Eng.

## RC#7 Linear Regression

>  By TA: DONG Juechu, Mar. 2021

if you want to edit this note, you can find it here https://github.com/joydddd/VE401-2021SP-notes



### Simple Linear Regression

$$
Y \mid x=\beta_{0}+\beta_{1} x+E
$$
where $\mathrm{E}[E]=0$

#### Least Square Method



For each measurement $y_{i}$ find residual $e_{i}$
$$
Y_{i}=b_{0}+b_{1} x_{i}+e_{i}
$$
error sum of squares:
$$
\begin{array}{l}
\mathrm{SS}_{\mathrm{E}}:=e_{1}^{2}+e_{2}^{2}+\cdots+e_{n}^{2}=\sum_{i=1}^{n}\left(y_{i}-\left(b_{0}+b_{1} x_{i}\right)\right)^{2} \\
\end{array}
$$
least-squares estimates for $\beta_{0}$ and $\beta_{1}$ is determined by minimizing this sum of squares
$$
\begin{array}{rlr}
S_{x x}& :=\sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)^{2}, S_{y y}:=\sum_{i=1}^{n}\left(y_{i}-\bar{y}\right)^{2}, \\
S_{x y} & :=\sum_{i=1}^{n}\left(x_{i}-\bar{x}\right)\left(y_{i}-\bar{y}\right) . \\
b_{0} &=\bar{y}-b_{1} \bar{x}, \quad b_{1}=\frac{S_{x y}}{S_{x x}}\\
\mathrm{SS}_{\mathrm{E}} & =S_{y y}-b_{1} S_{x y}\\
\end{array}
$$
with confidence interval
$$
B_{1} \pm t_{\alpha / 2, n-2} \frac{S}{\sqrt{S_{x x}}}, \quad B_{0} \pm t_{\alpha / 2, n-2} \frac{S \sqrt{\sum x_{i}^{2}}}{\sqrt{n S_{x x}}}
$$
#### Significance Test

 We reject
$$
H_{0}: \beta_{1}=0
$$
at significance level $\alpha$ if the statistic
$$
T_{n-2}=\frac{B_{1}}{S / \sqrt{S_{x x}}}
$$
satisfies $\left|T_{n-2}\right|>t_{\alpha / 2, n-2} .$

#### Test for Correlation

##### Coefficient

$$
R^{2}:=\frac{S S_{T}-S S_{E}}{S S_{T}}=\frac{S_{x}^{2}}{S_{x} S_{yy}}=\hat{\rho}_{X Y}^{2} \text { (in Paired T-tast) }
$$
The coefficient $R^{2}$ expresses the proportion of the total variation in $Y$ that is explained by the linear model



Let $(X, Y)$ follow a bivariate normal distribution with correlation coefficient $\varrho \in(-1,1)$. Let $R$ be the estimator (22.1) for $\varrho$. Then
$$
H_{0}: \varrho=0
$$
is rejected at significance level $\alpha$ if
$$
\left|\frac{R \sqrt{n-2}}{\sqrt{1-R^{2}}}\right|>t_{\alpha / 2, n-2}
$$

#### Lack of Fit Test


$$
SS_{E} = SS_{E,pe} + SS_{E,lf}
$$
pr: pure error, lf: lack of fitting (X & Y are not linearly related)
$$
\mathrm{SS}_{\mathrm{E}, \mathrm{pe}}:=\sum_{i=1}^{k} \sum_{j=1}^{n_{i}}\left(Y_{i j}-\bar{Y}_{i}\right)^{2}
$$
$H_{0}:$ the linear regression model is appropriate
is rejected at significance level $\alpha$ if the test statistic
$$
F_{k-2, n-k}=\frac{S S_{E, \text { If }} /(k-2)}{S S_{E, p e} /(n-k)}
$$
satisfies $F_{k-2, n-k}>f_{\alpha, k-2, n-k} .$

### Prediction

100(1-$\alpha$)% Prediction interval for $Y \mid x$ :
$$
\widehat{Y \mid x} \pm t_{\alpha / 2, n-2} S \sqrt{1+\frac{1}{n}+\frac{(x-\bar{x})^{2}}{S_{x x}}}
$$
 $100(1-\alpha) \%$ confidence interval for
$\mu_{Y \mid x}:$
$$
\widehat{\mu}_{Y \mid x} \pm t_{\alpha / 2, n-2} S \sqrt{\frac{1}{n}+\frac{(x-\bar{x})^{2}}{S_{x x}}}
$$