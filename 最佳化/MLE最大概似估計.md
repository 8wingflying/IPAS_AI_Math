## 1. 最大概似估計（Maximum Likelihood Estimation, MLE）
- 最大概似估計是一種統計方法，用來根據觀察資料估計模型的參數。
- 其核心思想是：**找到使觀察到的資料最有可能出現的參數值**。

---

## 2. 概似函數（Likelihood Function）

給定資料  

$$
x_1, x_2, \\ldots, x_n
$$

假設資料服從某個含參數 $ \theta $ 的機率分布，則「概似函數」定義為：

$$
L(\theta) = f(x_1|\theta) f(x_2|\theta) \\, \\cdots \\, f(x_n|\theta)
$$

常用「對數概似」（log-likelihood）簡化計算：

$$
\ell(\theta) = \log L(\theta)
$$

---

## 3. MLE 的核心步驟

1. **寫出機率模型**（例如常態分布、伯努利分布）
2. **寫出概似函數**
3. **取對數概似**
4. **對參數求導並求最大值**
5. **得到參數估計值**

---

## 4. 例子：常態分布 MLE 推導

假設資料服從：

$$
X \sim N(\\mu, \\sigma^2)
$$

對 $$ \mu, \sigma^2 $$ 進行 MLE。

### 4.1 對數概似：

$$
\ell(\mu, \sigma^2) = -\frac{n}{2}\log (2\pi \sigma^2)
 - \frac{1}{2\sigma^2} \sum_{i=1}^n (x_i - \\mu)^2
$$

### 4.2 求導、令其為零

結果得到：

$$
\hat{\mu} = \frac{1}{n} \sum x_i
$$

$$
\hat{\sigma}^2 = \frac{1}{n} \sum (x_i - \hat{\\mu})^2
$$

---

## 5. Python 實作：以 MLE 估計常態分布參數

```python
import numpy as np
from scipy.optimize import minimize

# 假設資料
data = np.array([2.3, 2.5, 1.8, 3.0, 2.7, 2.9])

# 對數概似函數
def neg_log_likelihood(params):
    mu, sigma = params[0], params[1]
    if sigma <= 0:
        return np.inf
    return -np.sum(-np.log(np.sqrt(2*np.pi)*sigma) - (data - mu)**2 / (2*sigma**2))

# 初始猜測
initial = [0, 1]

result = minimize(neg_log_likelihood, initial)
mu_mle, sigma_mle = result.x

print("MLE μ =", mu_mle)
print("MLE σ =", sigma_mle)
