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

$$\begin{equation} 
\rho_w 4\pi R^2 \frac{dR}{dt} = D n_o \int \delta^{(3)}(\mathbf{r}-\mathbf{R}) r dr d\Omega = 4\pi D n_o R \\
\end{equation}$$

$$\Rightarrow \frac{dR}{dt} \propto \frac{1}{R}$$

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

[fig1a]: {{site.baseurl}}/img/post-physics-sce-fig1a.jpg "Big drop through sea of small droplets" 
[fig1b]: {{site.baseurl}}/img/post-physics-sce-fig1b.jpg "Volume swept" 

| ![][fig1a] | ![][fig1b]|
|:--------:|:---------:|
|*Big drop falling through the sea of the small droplets*|*Volume swept by big droplet through sea of small droplets*|

[Fig. 1(b)](#fig1b) shows that size-1 droplet sweeps volume at a rate of $\pi (r_1 + r_2)^2 \delta v$. 
For now let us assume that all size-2 droplets encountered by size-1 droplet gets absorbed 
and lead to increase in volume at a rate of 

$$
\frac{d\mathcal{V}}{dt} = \pi (r_1 + r_2)^2 \delta v \times N_2
$$

The total number of collision between size-1 and size-2 group is given by 
$\pi (r_1 + r_2)^2 \delta v \times N_1 N_2$. Since the process of coagulation is stochastic, 
the above formula gives average rate of collision between size-1 and size-2 groups. Now we 
can generalise the approach to system with any number of size groups, by allowing a 
distribution for number density $n(x)$, here $x$ can be radius, log(radius) or volume, but 
for now let us assume $x$ represent volume unless otherwise mentioned. Let us make the 
following identification. 

$$\begin{equation}
N_1 \rightarrow n(x_1,t) dx_1; N_2 \rightarrow n(x_2,t) dx_2
\label{two-groups-rate}
\end{equation}$$

The equation~$\eqref{two-groups-rate}$ can be used to write down the probability that a 
size-$x_1$ collide with a size-$x_2$ droplet in time interval $t$ to $t+dt$ as

$$\begin{equation}
(n(x_1, t) n(x_2, t) K(x_1, x_2) dx_1 dx_2 dt
\label{collision-prob}
\end{equation}$$

where $K(x_1, x_2)$ is kernel for coagulation\footnote{collision followed by coalescence}. 
In above case, $K(x_1, x_2) = \pi (r_1 + r_2)^2 \delta v E(x_1, x_2)$ this is called 
gravitational or geometric kernel. $E(x_1, x_2)$ is the called the efficiency of coagulation. 
In our case, we assumed that any droplet in the sweeped volume will definitely collide and 
coalesce. This means in our case $E(x_1, x_2) = 1$. Efficiency is dependent on various 
factors, namely, 

1. hydrodynamic interactions among the droplets, 
2. turbulence flow of  background field, 
3. Electric field etc.
