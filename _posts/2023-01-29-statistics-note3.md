---
layout: post
read_time: true
show_date: true
title:  Statistics Note3
date:   2023-01-28 19:30:20 -0600
description: Statistics Note3.
tags: [statistics]
author: zQqingqing
img: posts/20230109/statistics1.png 
github:  
mathjax: yes
---

# Statistics

This is note3 based on  *Linear Algebra And Learning From Data* by *Gilbert Strang*.

---

### 1.Covariance Matrices and Joint Probabilities  
Linear algebraenters When we run M different experiments. For example, we measure **age and height and weight** to get a vector $m=(m_1,m_2,m_3)$ in which $m=3$.  

A matrix becomes involved when we look at variances. Each experiment (dimension) will have a sample variance or expected variance.  If we measure age and height and weight for children, the results will be strongly **correlated**. The connection of variables is denoted by **covariance**.   

$$\sigma_{12}=E[(m_1-\mu_1)(m_2-\mu_2)]$$  
also:
$$\sigma_{xy}=E[(X-\bar X)(Y-\bar Y)]$$  
Joint probability $p_{ij}$ : experiment1 produces i and experiment2 produces j.  
$$\sigma_{12}=\sum_{i}\sum_{j}p_{ij}(x_i-m_1)(y_j-m_2)$$  

Probability Matrix:  
$$
\begin{pmatrix}
	p_{11} & p_{12}  \\
	p_{21} & p_{22}  \\
\end{pmatrix}
$$  

For independent trials we have $\sigma_{ij}(i\ne j) = 0$ , because $p_{ij}=p_ip_j$  

Covariance Matrix (By definition):  
$$V = \sum \sum p_{ij}
\begin{pmatrix}
	(x_i-m_1)^2 & (x_i-m_1)(y_j-m_2)  \\
	(x_i-m_1)(y_j-m_2) & (y_j-m_2)^2  \\
\end{pmatrix}
$$  

On the diagonal, we are getting the ordinary variances $\sigma_1^2, \sigma_2^2$ :  
$$V_{11} = \sum\sum  p_{ij}	(x_i-m_1)^2=\sum p_i	(x_i-m_1)^2=\sigma_{1}^2$$  

We can write V in vector multiplication form:  

$
\begin{bmatrix}
	(x_i-m_1)^2 & (x_i-m_1)(y_j-m_2)  \\
	(x_i-m_1)(y_j-m_2) & (y_j-m_2)^2  \\
\end{bmatrix}
$ $=\begin{bmatrix}
	x_i-m_1 \\
	y_j-m_2   \\
\end{bmatrix} \begin{bmatrix}
	x_i-m_1 & y_j-m_2  \\
\end{bmatrix}$  

$=(X-\bar X)(X-\bar X)^T$

We know that V is **sum of rank 1 matrices** and **symmetric** matrix (Positive Semidefinite also).  
$$V=\sum p_{ij}(X-\bar X)(X-\bar X)^T$$  
for continous r.v.:  
$$V=\int p_{ij}(X-\bar X)(X-\bar X)^T$$  

#### The covariance matrix for $Z=AX$  

$Z=AX$, $V_z=AV_XA^T$ 

Example:  

$A=\begin{bmatrix}
	1 & 1  \\
\end{bmatrix}$ ,  $Z=X+Y$  

$$\sigma_z^2=\begin{bmatrix}1&1 \end{bmatrix}\begin{bmatrix}\sigma_x^2&\sigma_{xy}\\\sigma_{xy}& \sigma_y^2 \end{bmatrix}\begin{bmatrix}1\\1 \end{bmatrix}=\sigma_x^2+\sigma_y^2+2\sigma_{xy}$$


#### The Correlation $\rho$  
Correlation $\rho _{xy}$  
$$-1\le \rho _{xy}=\frac{\sigma_{xy}}{\sigma_x\sigma_y} \le1$$  
Standardize $X=\frac{x}{\sigma_x}$, $Y=\frac{y}{\sigma_y}$,$\rho_{xy}=$ covariance of X and Y.  