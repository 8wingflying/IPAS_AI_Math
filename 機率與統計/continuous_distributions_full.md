# 連續機率分布：完整教學檔（含 PDF 公式、Python 程式碼）

本文件整理 **20 種常見連續機率分布**，每個分布包含：

-   機率密度函數（PDF）
-   累積分布函數（CDF）
-   期望 / 變異數
-   Python 產生方法（`scipy.stats`）
-   若適用則包含示意圖（附前面三種）

------------------------------------------------------------------------

# 1. 常態分布（Normal Distribution）

PDF： \[ f(x)=`\frac{1}{\sqrt{2\pi\sigma^2}}`{=tex}
e\^{-`\frac{(x-\mu)^2}{2\sigma^2}`{=tex}} \]

CDF： \[
F(x)=`\frac{1}{2}`{=tex}`\left[1+\operatorname{erf}\left(\frac{x-\mu}{\sigma\sqrt{2}}\right)\right]`{=tex}\]

期望：( `\mu `{=tex})\
變異數：( `\sigma`{=tex}\^2 )

Python：

``` python
from scipy.stats import norm
x = norm.rvs(loc=0, scale=1, size=1000)
pdf = norm.pdf(x)
```

![](normal.png)

------------------------------------------------------------------------

# 2. 指數分布（Exponential Distribution）

PDF： \[ f(x)=`\lambda `{=tex}e\^{-`\lambda `{=tex}x}, ; x`\ge 0`{=tex}
\]

期望：( 1/`\lambda `{=tex})\
變異數：( 1/`\lambda`{=tex}\^2 )

Python：

``` python
from scipy.stats import expon
x = expon.rvs(scale=1, size=1000)
```

![](exponential.png)

------------------------------------------------------------------------

# 3. 均勻分布（Uniform Distribution）

PDF： \[ f(x)=`\frac{1}{b-a}`{=tex} \]

期望：( (a+b)/2 )\
變異數：( (b-a)\^2/12 )

Python：

``` python
from scipy.stats import uniform
x = uniform.rvs(loc=0, scale=1, size=1000)
```

![](uniform.png)

------------------------------------------------------------------------

# 4. Beta 分布（Beta Distribution）

PDF： \[
f(x)=`\frac{x^{\alpha-1}(1-x)^{\beta-1}}{B(\alpha,\beta)}`{=tex} \]

Python：

``` python
from scipy.stats import beta
x = beta.rvs(2,5,size=1000)
```

------------------------------------------------------------------------

# 5. Gamma 分布（Gamma Distribution）

PDF： \[ f(x)=`\frac{1}{\Gamma(k)\theta^k}`{=tex} x\^{k-1}
e\^{-x/`\theta`{=tex}} \]

Python：

``` python
from scipy.stats import gamma
x = gamma.rvs(2,2,size=1000)
```

------------------------------------------------------------------------

# 6. 對數常態分布（Lognormal）

\[ X = e\^Y, Y `\sim `{=tex}N(`\mu`{=tex},`\sigma`{=tex}\^2) \]

Python：

``` python
from scipy.stats import lognorm
x = lognorm.rvs(1, size=1000)
```

------------------------------------------------------------------------

# 7. 拉普拉斯分布（Laplace）

PDF： \[ f(x)=`\frac{1}{2b}`{=tex}e\^{-\|x-`\mu`{=tex}\|/b} \]

Python：

``` python
from scipy.stats import laplace
x = laplace.rvs(size=1000)
```

------------------------------------------------------------------------

# 8. 柯西分布（Cauchy Distribution）

PDF： \[ f(x)=`\frac{1}{\pi(1+x^2)}`{=tex} \]

Python：

``` python
from scipy.stats import cauchy
x = cauchy.rvs(size=1000)
```

------------------------------------------------------------------------

# 9. 卡方分布（Chi-square）

Python：

``` python
from scipy.stats import chi2
x = chi2.rvs(df=4, size=1000)
```

------------------------------------------------------------------------

# 10. t 分布（Student-t）

Python：

``` python
from scipy.stats import t
x = t.rvs(df=10, size=1000)
```

------------------------------------------------------------------------

# 11. F 分布

Python：

``` python
from scipy.stats import f
x = f.rvs(5,2,size=1000)
```

------------------------------------------------------------------------

# 12. Weibull 分布

Python：

``` python
from scipy.stats import weibull_min
x = weibull_min.rvs(c=1.5,size=1000)
```

------------------------------------------------------------------------

# 13. Pareto 分布

Python：

``` python
from scipy.stats import pareto
x = pareto.rvs(3,size=1000)
```

------------------------------------------------------------------------

# 14. Rayleigh 分布

Python：

``` python
from scipy.stats import rayleigh
x = rayleigh.rvs(size=1000)
```

------------------------------------------------------------------------

# 15. Gumbel（極值分布 I）

Python：

``` python
from scipy.stats import gumbel_r
x = gumbel_r.rvs(size=1000)
```

------------------------------------------------------------------------

# 16. Frechet（極值分布 II）

（可用 `genextreme` 模擬）

Python：

``` python
from scipy.stats import genextreme
x = genextreme.rvs(-0.5,size=1000)
```

------------------------------------------------------------------------

# 17. Logistic 分布

Python：

``` python
from scipy.stats import logistic
x = logistic.rvs(size=1000)
```

------------------------------------------------------------------------

# 18. Maxwell-Boltzmann 分布

Python：

``` python
from scipy.stats import maxwell
x = maxwell.rvs(size=1000)
```

------------------------------------------------------------------------

# 19. Log-Gamma 分布

Python：

``` python
from scipy.stats import loggamma
x = loggamma.rvs(1,size=1000)
```

------------------------------------------------------------------------

# 20. Power Law（冪律分布）

Python：

``` python
from scipy.stats import powerlaw
x = powerlaw.rvs(5,size=1000)
```

------------------------------------------------------------------------

（若需要我可以加入每個分布的示意圖）
