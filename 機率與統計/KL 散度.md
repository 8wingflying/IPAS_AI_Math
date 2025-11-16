# KL Divergence（Kullback–Leibler Divergence）

---

## 📘 1. 什麼是 KL Divergence？

**KL 散度（Kullback–Leibler Divergence）** 是用來衡量兩個機率分布  
**P（真實分布）** 與 **Q（近似分布）** 之間差異的「不對稱距離」。

它衡量：  
> 使用 Q 近似 P 時，損失了多少資訊（information loss）

---

# 📐 2. KL Divergence 定義公式

## 📌 離散分布

$$
D_{KL}(P \| Q)=\sum_x P(x)\log\frac{P(x)}{Q(x)}
$$

---

## 📌 連續分布

$$
D_{KL}(P \| Q)=\int_{-\infty}^{\infty} p(x)\log\frac{p(x)}{q(x)} dx
$$

---

# 🔎 3. KL Divergence 的性質

| 性質 | 說明 |
|------|------|
| 非負性 | $D_{KL}(P\|Q) \ge 0$（Gibbs不等式） |
| 不對稱 | $D_{KL}(P\|Q) \ne D_{KL}(Q\|P)$ |
| 不是真正的距離 | 因為不對稱、也不滿足三角不等式 |
| 0 代表分布完全相同 | $P=Q$ 時 KL=0 |

---

# 📊 4. 常見例子：兩個常態分布的 KL Divergence

若

$$
P = \mathcal{N}(\mu_1,\sigma_1^2), \quad 
Q = \mathcal{N}(\mu_2,\sigma_2^2)
$$

則

$$
D_{KL}(P\|Q)=
\log\frac{\sigma_2}{\sigma_1}
+ \frac{\sigma_1^2 + (\mu_1-\mu_2)^2}{2\sigma_2^2}
-\frac{1}{2}
$$

---

# 🧪 5. SymPy 計算 KL Divergence（離散）

```python
import sympy as sp

# 定義離散機率
p1, p2 = sp.Rational(1,2), sp.Rational(1,2)
q1, q2 = sp.Rational(1,4), sp.Rational(3,4)

# KL divergence
KL = p1*sp.log(p1/q1) + p2*sp.log(p2/q2)
KL.simplify()
🧪 6. SymPy 計算 KL Divergence（連續 Normal）
python
永遠顯示詳細資料

複製程式碼
import sympy as sp

mu1, mu2 = sp.symbols('mu1 mu2', real=True)
s1, s2 = sp.symbols('s1 s2', positive=True)

KL = sp.log(s2/s1) + (s1**2 + (mu1-mu2)**2)/(2*s2**2) - sp.Rational(1,2)
sp.simplify(KL)
