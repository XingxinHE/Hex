# 📝Definition
- A regression model is (the [[Affine Function]] of $x$)
  $$
  \hat{y} = x^T\beta+v
  $$
  with
    - $x$, a $n$-vector a.k.a. **feature** vector
        - $x_1,x_2,...,x_n$ are called regressor
        
    - $\beta$, a $n$-vector, a.k.a. <u>weight vector / coefficient vector</u>
    - $v$, a scalar, a.k.a. <u>offset / intercept</u>
    - $\hat{y}$, the $\hat{}$ symbol indicating it is an <u>estimate / prediction</u>
    - $y$, dependent variable, a.k.a. <u>output labels</u>
    
- Side Notes⭐
    - $\beta, v$ are both **parameters tuning** this regression model.
    - $\beta$ is a weight vector which indicates the dependence between input and the performance of model.
        - e.g. $\beta_{13}$ is bigger, $x_{13}$ has more significant effect on the model
        - e.g. $\beta_{27}$ is smaller, $x_{27}$ has less effect on the model
        
# 🧮Notation
- 📌Simplified Regression Model Notation
    - Although I think this notation is kind of useless... Anyhow... the following is its equation.
      $$
      \hat{y}=x^T\beta+v=\begin{bmatrix}1\\x\end{bmatrix}^T\begin{bmatrix}v\\\beta\end{bmatrix}
      $$
      The dimension of $1,v$ are 1.
    - The dimension of $x,\beta$ are $n$.
    - Literally no difference from the left hand side.
    
# 🤳Applicability
- What are the situations in which this subject can be applied?
- 📌House price regression model
    - Suppose:
        - $y$, the actual selling price of the house
        - $x_1$, the house area
        - $x_2$, the number of bedrooms
        - $\hat{y}$, the estimate price
        
    - Then we have:
        - $$
          \hat{y}=x^T\beta+v=\beta_1x_1+\beta_2x_2+v
          $$
        
    - As a specific numerical example, consider the regression model parameters:
      $$
      \beta=(148.73,-18.85), \quad v=54.40
      $$
        - $\beta_1>0$, it is easy to understand, house area⬆, price⬆
        - $\beta_2<0$, this is hard to understand, maybe because increasing the number of rooms with same area will be considered as a public house?..(公租房)
        - $v>0$, considering when $x_1=0,x_2=0$, then $v=54.40$, that is the value of the lot.(土地价格)
        