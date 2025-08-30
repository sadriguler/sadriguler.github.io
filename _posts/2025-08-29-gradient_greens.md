---
layout: post
title: Gradient of the Green's function
date: 2025-08-29 00:30:00-0400
description: a step by step implementation
tags: electromagnetics
categories: cem
related_posts: false
---
For an observation vector $$\vec r =x\hat{i} + y\hat{j} + z\hat{k}$$ and a source vector on $$\vec r^\prime=x^\prime\hat{i} + z^\prime\hat{i} + z^\prime\hat{k}$$, the Green’s function for the homogeneous electromagnetic scattering problems is

\begin{equation}
\label{start_eq}
g(\vec r - \vec r^\prime)=\frac{e^{ikR}}{4\pi R},
\end{equation}

where the difference vector is $$\vec R = \vec r-\vec r^\prime$$ and its length is $$ R = \|\vec R\| $$. The gradient operator in the cartesian coordinates is

$$
\nabla = \frac{\partial }{\partial x}\hat{\imath} + \frac{\partial }{\partial y}\hat{\jmath} +\frac{\partial }{\partial k}\hat{z}.
$$

The gradient of the Green’s function is

$$
\nabla g=\frac{1}{4\pi R}\nabla e^{ikR} + e^{ikR}\nabla\frac{1}{4\pi R}
$$

by the product rule. Using the differentiation of exponential and the quotient rule, the gradient is

$$
\nabla g = \frac{1}{4\pi R}\cdot ik\cdot e^{ikR}\cdot \nabla R + e^{ikR}\cdot\frac{1}{4\pi}\cdot\frac{-1}{R^2}\cdot\nabla{R}
$$

and the formula is further organized as

$$
\nabla{g}=\frac{e^{ikR}}{4\pi R}\cdot ik\cdot \nabla{R} - \frac{e^{ikR}}{4\pi R}\cdot\frac{1}{R}\nabla{R}
$$

and 

$$
\nabla{g}=\frac{ikR}{4\pi R}\Big(ik-\frac{1}{R} \Big)\nabla{R}.
$$

For the defined $$\vec r$$ and $$\vec r^\prime$$, the difference vector is written explicitly

$$
R = \sqrt{(x-x^\prime)^2 + (y-y^\prime)^2 + (z-z^\prime)^2}.
$$

The gradient of $$R$$ is

$$
\nabla{R}=\frac{\partial{R}}{\partial x}\hat{i}+ \frac{\partial{R}}{\partial y}\hat{j} + \frac{\partial{R}}{\partial z}\hat{k}.
$$

The partial derivative of the $$x$$ component is 

$$
\frac{\partial R}{\partial x} = \frac{1}{2}\frac{2\cdot\frac{\partial(x-x^\prime)}{\partial{x}}\cdot(x -x^\prime)}{\sqrt{(x-x^\prime)^2 + (y-y^\prime)^2 + (z-z^\prime)^2}}.
$$

The organization of the equation gives

$$
\frac{\partial R}{\partial x}=\frac{x-x^\prime}{R}.
$$

The result for the differentiation of the $$x$$ component also defines the partial component of the $$y$$ and $$z$$ components and the gradient of the distance $$R$$ is

$$
\nabla R=\frac{x-x^\prime}{R}\hat{i} + \frac{y-y^\prime}{R}\hat{j} + \frac{z-z^\prime}{R}\hat{k},
$$

which takes the form

$$
\nabla R = \frac{\vec r - \vec r^\prime}{R}=\frac{\vec R}{R}.
$$

Therefore, the unit distance vector is $$\hat R = \frac{\vec R}{R}=\nabla R$$. The gradient of the Green’s function is 

$$
\nabla g=\Big(ik - \frac{1}{R}\Big)\frac{e^{ikR}}{4\pi R}\hat{R}.
$$

Finally, after the simplifications, the gradient of the Green’s function is

$$
\nabla{g(\vec r - \vec r^\prime)}=\Big(ik-\frac{1}{|\vec r - \vec r^\prime|}\Big)\frac{\vec r - \vec r^\prime}{|\vec r - \vec r^\prime|}g(\vec r - \vec r^\prime).
$$