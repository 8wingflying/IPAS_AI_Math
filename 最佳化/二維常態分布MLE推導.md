# 二維常態分布（Bivariate Normal Distribution）MLE 推導 — 教學講義

以下內容完整呈現二維常態分布 MLE 的推導，包含 PDF、似然、對數似然、對平均向量與共變異數矩陣的極大似然估計推導。

---

## 1. 問題設定

假設有 \(n\) 筆樣本：

$$
\mathbf{x}_i =
\begin{pmatrix}
x_{i1}\\
x_{i2}
\end{pmatrix},\quad i = 1,\dots,n,
$$

來自二維常態分布：

$$
\mathbf{x}_i \sim \mathcal{N}_2(\boldsymbol{\mu}, \Sigma),
$$

其中：

$$
\boldsymbol{\mu} =
\begin{pmatrix}
\mu_1 \\
\mu_2
\end{pmatrix},
\quad
\Sigma =
\begin{pmatrix}
\sigma_1^2 & \rho\sigma_1\sigma_2 \\
\rho\sigma_1\sigma_2 & \sigma_2^2
\end{pmatrix}.
$$

---

## 2. 二維常態分布的密度函數

$$
f(\mathbf{x}\mid\boldsymbol{\mu},\Sigma)
=
\frac{1}{2\pi |\Sigma|^{1/2}}
\exp\left(
-\frac{1}{2}
(\mathbf{x}-\boldsymbol{\mu})^T
\Sigma^{-1}
(\mathbf{x}-\boldsymbol{\mu})
\right),
$$

其中：

$$
|\Sigma|=\sigma_1^2\sigma_2^2(1-\rho^2).
$$

---

## 3. 似然函數與對數似然

i.i.d 假設下：

$$
L=\prod_{i=1}^n f(\mathbf{x}_i)
$$

取 log：

$$
\ell
=
-\frac{n}{2}\log(2\pi)
-\frac{n}{2}\log|\Sigma|
-\frac{1}{2}\sum_{i=1}^n(\mathbf{x}_i-\boldsymbol{\mu})^T\Sigma^{-1}(\mathbf{x}_i-\boldsymbol{\mu}).
$$

忽略與參數無關的常數後：

$$
\ell
=
-\frac{n}{2}\log|\Sigma|
-\frac{1}{2}\sum_{i=1}^n(\mathbf{x}_i-\boldsymbol{\mu})^T\Sigma^{-1}(\mathbf{x}_i-\boldsymbol{\mu}).
$$

---

## 4. 平均向量 \( \mu \) 的 MLE 推導

考慮：

$$
Q=\sum_{i=1}^n(\mathbf{x}_i-\boldsymbol{\mu})^T \Sigma^{-1}(\mathbf{x}_i-\boldsymbol{\mu}).
$$

微分：

$$
\frac{\partial Q}{\partial\boldsymbol{\mu}}
= -2\Sigma^{-1}\sum_{i=1}^n(\mathbf{x}_i-\boldsymbol{\mu}).
$$

因此：

$$
\frac{\partial\ell}{\partial\mu}
=
\Sigma^{-1}\sum_{i=1}^n(\mathbf{x}_i-\boldsymbol{\mu})
=0.
$$

得到：

$$
\hat{\boldsymbol{\mu}}=\frac{1}{n}\sum_{i=1}^n\mathbf{x}_i.
$$

---

## 5. 共變異數矩陣 \( \Sigma \) 的 MLE 推導

設中心化矩陣：

$$
\mathbf{x}_i^c = \mathbf{x}_i - \hat{\boldsymbol{\mu}}.
$$

定義：

$$
C=\sum_{i=1}^n \mathbf{x}_i^c(\mathbf{x}_i^c)^T.
$$

對數似然寫成 trace：

$$
\ell=
-\frac{n}{2}\log|\Sigma|
-\frac{1}{2}\mathrm{tr}(\Sigma^{-1}C).
$$

使用微分公式：

$$
\frac{\partial}{\partial\Sigma}\log|\Sigma| = \Sigma^{-1},
$$
$$
\frac{\partial}{\partial\Sigma}\mathrm{tr}(\Sigma^{-1}C)
= -\Sigma^{-1}C\Sigma^{-1}.
$$

因此：

$$
\frac{\partial\ell}{\partial\Sigma}
=
-\frac{n}{2}\Sigma^{-1}
+\frac{1}{2}\Sigma^{-1}C\Sigma^{-1}=0.
$$

化簡後：

$$
C = n\Sigma.
$$

得到：

$$
\hat{\Sigma}
=
\frac{1}{n}\sum_{i=1}^n
(\mathbf{x}_i-\hat{\boldsymbol{\mu}})
(\mathbf{x}_i-\hat{\boldsymbol{\mu}})^T.
$$

---

## 6. 最終 MLE 結論

### **平均向量 MLE**

$$
\hat{\mu}_1=\frac{1}{n}\sum x_{i1},
\quad
\hat{\mu}_2=\frac{1}{n}\sum x_{i2}.
$$

### **共變異數矩陣 MLE**

$$
\hat{\Sigma}
=
\frac{1}{n}\sum_{i=1}^n
(\mathbf{x}_i-\bar{\mathbf{x}})
(\mathbf{x}_i-\bar{\mathbf{x}})^T.
$$

### **參數形式**

$$
\hat{\sigma}_1^2=\frac{1}{n}\sum (x_{i1}-\bar{x}_1)^2,
$$

$$
\hat{\sigma}_2^2=\frac{1}{n}\sum (x_{i2}-\bar{x}_2)^2,
$$

$$
\hat{\sigma}_{12}=\frac{1}{n}\sum
(x_{i1}-\bar{x}_1)(x_{i2}-\bar{x}_2),
$$

$$
\hat{\rho}
=
\frac{\hat{\sigma}_{12}}
{\sqrt{\hat{\sigma}_1^2 \hat{\sigma}_2^2}}.
$$

---


