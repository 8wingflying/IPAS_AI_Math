# 連續機率分布教學檔

## 1. 常態分布（Normal Distribution）

PDF: \[ f(x)=`\frac{1}{\sqrt{2\pi\sigma^2}}`{=tex}
e\^{-`\frac{(x-\mu)^2}{2\sigma^2}`{=tex}} \]

![](normal.png)

Python:

``` python
import numpy as np
from scipy.stats import norm
x = np.linspace(-4,4,400)
pdf = norm.pdf(x,0,1)
```

## 2. 指數分布（Exponential Distribution）

PDF: \[ f(x)=`\lambda `{=tex}e\^{-`\lambda `{=tex}x}, x`\ge 0`{=tex} \]

![](exponential.png)

Python:

``` python
from scipy.stats import expon
x = np.linspace(0,5,400)
pdf = expon.pdf(x,1)
```

## 3. 均勻分布（Uniform Distribution）

PDF: \[ f(x)=`\frac{1}{b-a}`{=tex} \]

![](uniform.png)

Python:

``` python
from scipy.stats import uniform
x = np.linspace(0,1,400)
pdf = uniform.pdf(x,0,1)
```

(其餘 17 種分布亦可依此格式擴充)
