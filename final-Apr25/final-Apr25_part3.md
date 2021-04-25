# VE401 Probabilistic Methods in Eng.

## # Final Review

>  By TA: DONG Juechu, April. 2021

if you want to edit this note, you can find it here https://github.com/joydddd/VE401-2021SP-notes

Mathematica code is also available on github. 

## Categorial Test

$$
f_{X_{1} X_{2} \cdots x_{k}}\left(x_{1}, \ldots, x_{k}\right)=\frac{n !}{x_{1} ! \cdots x_{k} !} p_{1}^{x_{1}} \cdots p_{k}^{x_{k}}
$$
$p_{1}, \ldots, p_{k} \in(0,1), n \in \mathbb{N} \backslash\{0\}$ is said to have a multinomial distribution with parameters $n$ and $p_{1}, \ldots, p_{k}$.

1. The (marginal) expectations of the individual random variables $X_{i}$ are given by

$$
\mathrm{E}\left[X_{i}\right]=n p_{i}, \quad i=1, \ldots, k .
$$
2. $\operatorname{Var}\left[X_{i}\right]=n p_{i}\left(1-p_{i}\right), i=1, \ldots, k$,
3. $\operatorname{Cov}\left[X_{i}, X_{j}\right]=-n p_{i} p_{j}, 1 \leq i<j \leq k$.

### Pearson Chi-squared Goodness of Fit Test

Test if the data follows ==multinomial distribution with parameters $(p_0, p_1, p_2 ... )$==
$$
H_{0}: p_{i}=p_{i_{0}}, \quad i=1, \ldots, k\\
X_{k-1}^{2}=\sum_{i=1}^{k} \frac{\left(X_{i}-n p_{i_{0}}\right)^{2}}{n p_{i_{0}}}
$$
We reject $H_{0}$ at significance level $\alpha$ if $X_{k-1}^{2}>\chi_{\alpha, k-1}^{2}$.

==Cochran's Rule==: make sure the chi-squared approximation is appropriate 

$$\mathrm{E}\left[X_{i}\right]=n p_{i} \geq 1$$ for all $i=1, \ldots, k$,

$$\mathrm{E}\left[X_{i}\right]=n p_{i} \geq 5$$ for $80 \%$ of all $i=1, \ldots, k$,
Especially if the $p_{i}$ are not known roughly beforehand, care needs to be taken to ensure that the sample size $n$ is sufficiently large so that these criteria can apply.

#### Categorical Test on Discrete Distribution

Test if the data follows ==a particular discrete distribution with m parameters estimated from the given data==

Divide our data into categories, use the discrete distribution to estimate the parameters, calculate the expected count of each category. 
$$
X_{k-1-m}^{2}= \sum_{1}^{k} \frac{\left(O_{i}-E_{i}\right)^{2}}{E_{i}}
$$

### Independence of Category

Test if ==the row and column categorizations are independent,== 
$$
H_{0}: p_{i j}=p_{i} \cdot p_{\cdot j}
$$

We can now compare the observed frequencies $O_{i j}$ in the $(i, j)$ th cell to the expected frequencies $E_{i j} .$ 
$$
X_{(r-1)(c-1)}^{2}=\sum_{i=1}^{r} \sum_{j=1}^{c} \frac{\left(O_{i j}-E_{i j}\right)^{2}}{E_{i j}} \\
E_{i j}=n \cdot \widehat{p_{i j}}=\frac{n_{i} \cdot n_{\cdot j}}{n}
$$
We reject $H_{0}$ if the value of $X_{(r-1)(c-1)}^{2}$ exceeds the critical value of the corresponding chi-squared distribution.
				
			

## Linear Regression

### Simple Linear Regression

==$$ Y \mid x=\beta_{0}+\beta_{1} x+E$$  where $\mathrm{E}[E]=0$==

$E$: remainder. $E[E] = 0$ is guaranteed because $b_0, b_1$ are unbiased estimators. 

$\beta_0, \beta_1$: true parameter of linear relationship. 

$b_0, b_1$: estimator for $\beta_0, \beta_1$. 

$B_0, B_1$ : statistics for estimators $b_0, b_1$



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
with ==confidence interval==
$$
B_{1} \pm t_{\alpha / 2, n-2} \frac{S}{\sqrt{S_{x x}}}, \quad B_{0} \pm t_{\alpha / 2, n-2} \frac{S \sqrt{\sum x_{i}^{2}}}{\sqrt{n S_{x x}}}
$$
#### Significance Test

We say that a regression is significant if there is statistical evidence that ==the slope $\beta_1 \neq 0$ .==

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
R^{2}:=\frac{S S_{T}-S S_{E}}{S S_{T}}=\frac{S_{x}^{2}}{S_{x} S_{yy}}=\hat{\rho}_{X Y}^{2} \text { (from Paired T-test) }
$$
The coefficient $R^{2}$ expresses the ==proportion of the total variation in $Y$ that is explained by the linear model==



Let $(X, Y)$ follow a bivariate normal distribution with correlation coefficient $\varrho \in(-1,1)$. Let $R$ be the estimator for $\varrho$. Then
$$
H_{0}: \varrho=0
$$
is rejected at significance level $\alpha$ if
$$
\left|\frac{R \sqrt{n-2}}{\sqrt{1-R^{2}}}\right|>t_{\alpha / 2, n-2}
$$

#### Lack of Fit Test

Test ==if the linear regression model is appropriate.==  Need ==multiple y data at each x== data point! 

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

==$$ Y \mid x=\beta_{0}+\beta_{1} x+E$$  where $\mathrm{E}[E]=0$==

$100(1-\alpha)\%$ ==Prediction interval== for $Y \mid x$ :
$$
\widehat{Y \mid x} \pm t_{\alpha / 2, n-2} S \sqrt{1+\frac{1}{n}+\frac{(x-\bar{x})^{2}}{S_{x x}}}
$$
 $100(1-\alpha) \%$ ==prediction interval== for $\mu_{Y} \mid x:$
$$
\widehat{\mu_Y \mid x} \pm t_{\alpha / 2, n-2} S \sqrt{\frac{1}{n}+\frac{(x-\bar{x})^{2}}{S_{x x}}}
$$