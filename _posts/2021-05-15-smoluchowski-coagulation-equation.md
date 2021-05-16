---
layout: post
title: Stochastic Collection Equation
tags: physics, cloud-droplet growth
categories: physics
mathjax: true
---

# A Back Story

A cloud forms by condensation of water vapour, as it reaches a given height. 
The condensation process is accelerated by aerosol particles of size $1\mu\textrm{m}$. 
These particles are called Cloud Condensation Nuclei (CCN). Due to condensation, in 
matter of minutes, we end up with very large number of (cloud) droplets with radius 
with radius of the order of $10 \mu\textrm{m}$. Growth rate of cloud droplets via 
this diffusive approach slows down with the increase of the radius. This can be shown 
as follows.

Consider the diffusion equation, $\mathbf{J}_{diff} = - D \mathbf{\nabla} n(\mathbf{r})$. 
The rate of inflow of material is given by, 

$$
\frac{dm}{dt}=-\oint \mathbf{J}_{diff}\cdot d\mathbf{A}
$$
 
This gives, 

$$
\rho_w 4\pi R^2 \frac{dR}{dt} = D \oint \mathbf{\nabla} n\cdot d\mathbf{A}
$$

Let $n(\mathbf{r}) = n_o \theta(\mathbf{r}-\mathbf{R})$

$$
\Rightarrow \mathbf{\nabla} n = n_o \delta^{(3)}(\mathbf{r}-\mathbf{R}) \hat{r}
$$
 
This implies,

$$\begin{eqnarray} 
\rho_w 4\pi R^2 \frac{dR}{dt} &= D n_o \int \delta^{(3)}(\mathbf{r}-\mathbf{R}) r dr d\Omega\\
&= 4\pi D n_o R 
\Rightarrow \frac{dR}{dt} &\propto \frac{1}{R}
\end{eqnarray}$$

This implies that growth of cloud droplets must occur via some other method. 

