---
title : Note1
feed: show
date : 19-11-2023
---
<head><link rel="stylesheet" type="text/css" href="_notes/note.css">
<script type="text/javascript" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>
</head>

| | **3 修改完成** |**10 代修改**|
| :--:| :----- | :-- |
|1 |  Sigma-Algebra  |  $\Sigma-$代数   |
|2|  Measurable Set | 可测集  |
|3|  Measure |测度  |
|4|Measurable Function  |可测函数 |
|5| Integration |积分 |
|6 |Monotone Convergence |单调收敛定理|
|7 | Dominated Convergence|控制收敛定理 |
|8 |Fatou's Lemma | Fatou引理 |
|9 |Approximation by Continuous Function |连续函数近似 |
|10 | the Definition of $\liminf_{n\to \infty}\&$ $\limsup_{n\to \infty}$ |上极限、下极限定义 |

::: block-1
### **1. Sigma-Algebra**:
A sigma-Algbra $\Sigma$ is a colleciton of subsets of $\Omega$ such that:

1. $\emptyset,\ \Omega\in \Sigma;$
2. If $A \in \Sigma$, then $A^c:=\Omega-A\in \Sigma;$
3. If $(A_n)_{n=1}^\infty\in \Sigma$, then $\cup_{n=1}^\infty A_n\in \Sigma.$
:::

::: block-1
### **2. Measurable Set**:
If $A\in \Sigma$, then $A$ is called measurable.
:::

::: block-1
### **3. Measure**:
A measure is a funciton $\mu:\Sigma\to [0,\infty]$ such that:
1. $\mu(A)\geq 0$ for all $A\in \Sigma$;
2. If $(A_n)_{n=1}^\infty\in \Sigma$, such that $A_n\cap A_m=\emptyset$ if $n\neq m$ then $\mu(\cup_{n=1}^\infty A_n)=\sum_{n=1}^\infty \mu(A_n)$.
:::

::: block-1
### **4. Measurable Function**:

- *Definition1*：Given a measurable space $(\Omega,\Sigma, \mu)$, a funciton $f:\Omega\to [0,\infty]$ is called measurable iff: the level sets $\{\boldsymbol{x}\in \Sigma\ |\  f(\boldsymbol{x})>t\}\in \Sigma$ for all $t\geq 0$.

- *Definition2*：$f(\boldsymbol{x})=\lim_{n\to \infty}f_n(x)$ where $f_n$ is a step function, i.e., $f_n(\boldsymbol{x})=\sum_{i=1}^I \lambda_i\chi_{A_i}$ where $\lambda_i\in \mathbb{R},\ A_i\in \Sigma$ and
$$\chi_{A_i}=\left \{\begin{array}{ll}1, & \text{if $\boldsymbol{x}\in A_i$}\\ 0, & \text{otherwise}\end{array}\right.$$


- *Defination3*：If $\Omega=\mathbb{R}^d$, $f(\boldsymbol{x})=\lim_{n\to \infty}f_n(\boldsymbol{x})$ where $f_n$ is a really simple function, i.e., $f_n(\boldsymbol{x})=\sum_{i=1}^I \lambda_i\chi_{A_i}$ where $\lambda_i\in \mathbb{R},\ A_i$ are cubes.
:::

>> ###
>>
>> In general, a function $f:\Omega\to \mathcal{C}$ can be split into $f=f_1-f_2+if_3-if_4$ with $f_i:\Omega\to [0,\infty]$ then $f$ is measurable iff all $f_i$ are.



::: block-1
### **5. Integration**:
For any measurable function: $f:\Omega\to [0,\infty]$, we define its Lebesgue integral to be
$$\int_{\Omega}f(\boldsymbol{x})d\mu(\boldsymbol{x})=\int_0^\infty\mu(\{\boldsymbol{x}\in \Sigma\ |\ f(\boldsymbol{x})>t\})dt$$
:::

> ### 5.1 Integrable function:
>
> For a measurable function $f:\Omega\to \mathcal{C}$, we define $$\int_\Omega f(\boldsymbol{x})d\mu(\boldsymbol{x})=\int f_1-\int f_2+i\int f_3-i\int f_4$$ which make sense iff $\int f_i<\infty$ for all $i\in \{1,2,3,4\}$. In this case, we call $f$ integrable function.

>> ###
>>
>> $f$ is integrable iff $|f|$ is measurable and $\int |f|<\infty$.


::: block-1
### **6. Monotone Convergence**:
If $(f_n)_{n=1}^\infty$ is a sequence of measurable, real integrable functions $f_n(\boldsymbol{x})\uparrow f(\boldsymbol{x})$ (i.e., $f_{n+1}(\boldsymbol{x})\geq f_n(\boldsymbol{x})$ for all $n\in \mathbb{N}$) for a.e. $\boldsymbol{x}$ (i.e., up to a set of measure 0) then $$\int_\Omega f(\boldsymbol{x})d\mu(\boldsymbol{x})=\lim_{n\to \infty}\int_\Omega f_n(\boldsymbol{x})d\mu(\boldsymbol{x})$$
- which holds even when both sides are $+\infty.$
:::

::: block-1
### **7. Dominated Convergence**:
If $(f_n)_{n=1}^\infty$ is a sequence of measurable, integrable functions ($f_n:\Omega\to \mathcal{C}$)
$$f_n(\boldsymbol{x})\stackrel{n\to \infty}{\longrightarrow}f(\boldsymbol{x})\ a.e. \boldsymbol{x}$$
and there exist an integrable function $G$,  such that $|f_n(\boldsymbol{x})|\leq G(\boldsymbol{x})$ for a.e. $\boldsymbol{x}$, then $$\int_\Omega f(\boldsymbol{x})d\mu (\boldsymbol{x})=\lim_{n\to \infty}\int_\Omega f_n(\boldsymbol{x})d\mu(\boldsymbol{x})$$
- both sides are finite.
:::

::: block-1
### **8. Fatou's Lemma**:
If $(f_n)_{n=1}^\infty$ is a sequence of integrable functions, $f_n\geq 0$, $f_n(\boldsymbol{x})\stackrel{n\to\infty}{\longrightarrow}f(\boldsymbol{x})$ a.e. $\boldsymbol{x}$ then
$$\liminf_{n\to \infty}\int_\Omega f_n(\boldsymbol{x})d\mu(\boldsymbol{x})\geq \int_\Omega f(\boldsymbol{x})d\mu(\boldsymbol{x})$$
:::

::: block-1
### **9. Approximation by Continuous Function**:
If $f:\mathbb{R}^d\to \mathcal{C}$ is an integrable function, then exists a sequence of functions with compact support (i.e., $f_n|_{K^c}\equiv 0$ for some compact set $K$) $(f_n)_{n=1}^\infty\subset \mathcal{C}_c(\mathbb{R}^d)$ such that
$$\int_{\mathbb{R}^d}|f_n-f|d\boldsymbol{x}\stackrel{n\to \infty}{\longrightarrow}0$$
:::

>> ###
>>
>> support $f=\overline{\{\boldsymbol{x}|\ f(\boldsymbol{x})\neq 0\}}$



::: block-1
### **10. the Definition of $\liminf_{n\to \infty} \&$ $\limsup_{n\to \infty}$**
- $\lim_{n\to \infty}a_n= a_0 \iff$ $\forall \epsilon>0, \exists N_\epsilon\in \mathbb{N},\ \forall n\geq N_\epsilon: |a_n-a_0|< \epsilon$
- $\liminf_{n\to \infty} a_n:=\lim_{n\to\infty}\inf_{m\geq n}a_m$
- $\limsup_{n\to \infty} a_n:=\lim_{n\to\infty}\sup_{m\geq n}a_m$
- $\liminf_{n\to \infty}a_n\geq a_0 \iff$ $\forall \epsilon>0, \exists N_\epsilon\in \mathbb{N},\ \forall n\geq N_\epsilon: a_n-a_0\geq -\epsilon$
- $\limsup_{n\to \infty}a_n\geq a_0 \iff$ $\forall \epsilon>0, \exists N_\epsilon\in \mathbb{N},\ \forall n\geq N_\epsilon: a_n-a_0\leq \epsilon$

:::
