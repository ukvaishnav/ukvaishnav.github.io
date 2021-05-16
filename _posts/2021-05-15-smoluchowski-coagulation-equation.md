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
&= 4\pi D n_o R \\
\Rightarrow \frac{dR}{dt} &\propto \frac{1}{R}
\end{eqnarray}$$

This implies that growth of cloud droplets must occur via some other method. 

# Simple Argument of Bi-dispersed cloud

Consider a bi-disperse cloud\footnote{Cloud with droplets of only two size groups.}. Let 
size-1 droplet has radius $r_1$, volume $x_1$ and number density, $N_1$. The same for size-2 
droplet. Assume that our droplets are stokesian i.e. the drag force experienced by them can 
be given by stokes law

$$
\mathbf{F}_{drag} = -6\pi \eta r \mathbf{v}
$$

This implies that the drops fall at their terminal speed given by
$v_{term} = \frac{2\rho g r^2}{9\eta}$. Hence the size-1 drops fall at speed $v_1$ where as 
all size-2 drops fall at speed $v_2$. Let us observe the motion of one size-1 droplet w.r.t. 
size-2 droplet.

[fig1a]: {{site.baseurl}}/img/post-physics-sce-fig1a.jpg "Image Title1" 
[fig1b]: {{site.baseurl}}/img/post-physics-sce-fig1b.jpg "Image Title2" 

| ![Big drop through sea of small droplets][fig1a] | ![Volume swept][fig1b]|
|:--------:|:---------:|
|*Big drop falling through the sea of the small droplets*|*Volume swept by big droplet through sea of small droplets*|


