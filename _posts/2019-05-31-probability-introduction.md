---
layout: post
title: "Probability Introduction"
date: 2019-05-31 21:37:05
image: '/assets/img/'
description:
tags:
categories:
twitter_text:
---

### Dirichlet Distribution

Let $\Theta  = \{\theta_1,\theta_2,\dots,\theta_m\}$, then $\Theta$ is parameters of a multinomial distribution. Dirichlet distribution is a **distribution over distribution**. The probability density function of Dirichlet distribution is 

$$P(\theta_1,\theta_2,\dots,\theta_m)= \frac{\Gamma(\sum_k \alpha_k)}{\prod_k\Gamma(\alpha_k)}\prod_{k=1}^m\theta_k^{\alpha_k-1}$$

where $\{\alpha_1,\alpha_2,\dots,\alpha_k\}$ is the parameters of the Dirichlet distribution.

### Dirichlet Process
Dirichlet Process is discribed by a sacling parameter $\alpha$ and a base distribution $G_0$, denoted as  $G\sim DP(\alpha,G_0)$

Assume we view these variables in a specific order, we get

$$X_n|X_1,\dots,X_{n-1} =\begin{cases} X_k &\mbox{w.p.} \frac{1}{n-1+\alpha}\\
\mbox{new draw from }G_0  &\mbox{w.p.} \frac{\alpha}{n-1+\alpha}
\end{cases}$$

Let there be only K unique values for $X_1\dots X_{n-1}$, then we can rewrite the formular above as 

$$X_n|X_1,\dots,X_{n-1} =\begin{cases} X^*_k &\mbox{w.p.} \frac{num_{n-1}(X_k^*)}{n-1+\alpha}\\
\mbox{new draw from }G_0  &\mbox{w.p.} \frac{\alpha}{n-1+\alpha}
\end{cases}$$

Something interesting is the density function of $X_1,\dots,X_{n}$ can be written as 

$$\frac{\alpha^K\prod_k (num(X_k^*)-1)!}{\alpha(1+\alpha)\dots(N-1+\alpha)} \prod_{k=1}^KG_0(X_k^*) $$

Note that, as the base distribution $G_0$ is continuos, the probability  that any two samples from this distribution is zero.

There are several interpretation for Dirichlet Process. One of famous interpretation is Chinese Restaurant Process. $X_n$ is the new customer. She/He is more willing to sit at a table if there are already many people sitting there, and She/He will sit at a new table with probability proportional to $\alpha$.


 
