# 線性代數
- 向量(Vector)運算
  - 點積（Dot Product） 
- 矩陣(Matrix)運算
  - 矩陣乘法（Matrix Multiplication）
  - 轉置（Transpose）
  - 矩陣求逆（Inverse）與偽逆（Pseudo-Inverse）
- 線性變換(Linear Transformation)與特徵空間(Feature Space)
  - 線性變換（Linear Transformation）
    - 縮放(Scaling):調整向量在各個方向上的長度，改變其尺度但不改變方向
    - 旋轉(Rotation):改變向量的方向而不改變其長度，常見於正交變換或特徵對齊
    - 剪切(Shearing):使向量方向在空間中產生傾斜變化，常出現在非對角矩陣的變換中。
    - 投影(Projection):將高維向量投射到某個子空間（如主成分空間或分類超平面），保留對任務最有意義的資訊
  - 特徵空間(Feature Space)
    - 資料中各個特徵所張成的數學空間，其中每一個軸代表一個特徵維度，每一筆資料可視為空間中的一個點。
    - 這個空間的幾何結構不僅描述了資料的分佈狀態，也影響了模型如何進行分類、迴歸或聚類等任務。 
  - 線性變換與特徵空間重構
- [解線性方程式](解線性方程式.md)
- 矩陣分解(Matrix Factorization)與維度簡化
  - [特徵值分解(Eigenvalue Decomposition)](EigenD.md)
    - 特徵值和特徵向量 https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors
    - https://en.wikipedia.org/wiki/Matrix_decomposition
  - [奇異值分解(Singular Value Decomposition, SVD)](SVD.md)
  - [非負矩陣分解(Non-negative Matrix Factorization, NMF)](NMF.md)
  - 維度簡化與學習效率的關聯
- 最小平方估計與線性迴歸


