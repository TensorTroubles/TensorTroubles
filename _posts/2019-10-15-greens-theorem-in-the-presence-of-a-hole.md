---
layout: post
title:  "Green's Theorem in the Presence of a Hole"
author: johnpiwinski
categories: [ Multivariate Calculus ]
tags: [featured]
---

## Subproblem 1: Green's Theorem of a Region with a Hole

Evaluate $$\int_C \left(e^{-x^2/2}-y\right)dx+\left(e^{-y^2/2}+x\right)dy$$ where $$C=C_1+C_2$$, $$C_{1}:x^2+y^2=25$$, $$C_{2}:\left(\frac{x}{2}\right)^2+y^2=1$$, and $$C_1$$ and $$C_2$$ are antiparallel.

Green's Theorem is defined as $$\int_{C}F\cdot dr=\displaystyle\int_{R}\int\left(\frac{\partial N}{\partial x}-\frac{\partial M}{\partial y}\right) dA$$ where $$F=Mdx+Ndy$$

First, we calculate $$\frac{\partial N}{\partial x}$$ and $$\frac{\partial M}{\partial y}$$ for $$F$$. $$\frac{\partial N}{\partial x}=\frac{\partial}{\partial x}\left(e^{-y^2/2}+x\right)=1$$ and $$\frac{\partial M}{\partial y}=\frac{\partial}{\partial y}\left(e^{-x^2/2}-y\right)=-1$$

Calculate the line integral of $$C_{1}:x^2+y^2=25$$ where $$r^2=x^2+y^2=25$$ and $$r=5$$

$$\int_{C_{1}} F \cdot dr = \displaystyle\int_{R_1}\int\left(\frac{\partial N}{\partial x} - \frac{\partial M}{\partial y}\right)dA=\int_{0}^{2\pi}\int_{0}^{5}1-(-1)rdrd\theta=\int_{0}^{2\pi}25d\theta=50\pi$$

Calculate the line integral of $$C_{2}:\left(\frac{x}{2}\right)^2+y^2=1$$ where $$x=2r\cos{\theta}$$ and $$y=r\sin{\theta}$$

$$\int_{C_{2}} F \cdot dr=\displaystyle\int_{R_2}\int\left(\frac{\partial N}{\partial x} - \frac{\partial M}{\partial y}\right)dA=\int_{\theta_i}^{\theta_f}\displaystyle\int_{r_i}^{r_f}\left(\frac{\partial N}{\partial X} - \frac{\partial M}{\partial y}\right)\begin{bmatrix}\frac{\partial x}{\partial r} & \frac{\partial x}{\partial \theta} \\ \frac{\partial y}{\partial r} & \frac{\partial y}{\partial \theta}\end{bmatrix}drd\theta=$$

$$\displaystyle\int_{0}^{2\pi}\displaystyle\int_{0}^{1}1 - (-1) \begin{bmatrix}2\cos{\theta} & -2r\sin{\theta} \\ \sin{\theta} & r\cos{\theta}\end{bmatrix}drd\theta=\displaystyle\int_{0}^{2\pi}\displaystyle\int_{0}^{1}2\left(2r\right)\left(\sin^2{\theta}+\cos^2{\theta}\right)drd\theta=4\pi$$
$$C_1$$ and $$C_2$$ are antiparallel: $$50\pi - 4\pi = 46\pi$$

## Subproblem 2: Stoke's Theorem on a Plane in the First Octant

Evaluate $$F(x, y, z) = -ln \sqrt{x^2+y^2} \hat{i} + \arctan\left( \frac{x}{y}\right) \hat{j} + \hat{k} $$ over the surface 2x + 3y + z = 9 and the section $$r=2\sin{2\theta}$$ in the $$1^{st}$$ octant.

Stoke's Theorem is defined as $$\int_{C} F \cdot dr = \int_S \int curl F \cdot N dS$$ where $$N =  2\hat{i} + 3\hat{j} + 1\hat{k} $$ for the surface.

Employ Sarrus' rule to determine the curl of $$F$$.$$curlF=\nabla \times F = \begin{bmatrix}\hat{i} & \hat{j} & \hat{k} & \hat{i} & \hat{j} \\ \frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} & \frac{\partial}{\partial x} & \frac{\partial}{\partial y} \\ -ln \sqrt{x^2+y^2} & \arctan \left( \frac{x}{y} \right)& 1 & -ln \sqrt{x^2+y^2} & \arctan \left( \frac{x}{y} \right)\end{bmatrix}$$

The curl of $$F$$ is $$\nabla \times F = \frac{\partial}{\partial y}1\hat{i} - \frac{\partial}{\partial z} ln{\sqrt{x^2 + y^2}}\hat{j} + \frac{\partial}{\partial x}\arctan \left({\frac{x}{y}}\right)\hat{k}+\frac{\partial}{\partial y}ln \sqrt{x^2+y^2}\hat{k}-\frac{\partial}{\partial z}\arctan \left(\frac{x}{y}\right)\hat{i}-\frac{\partial}{\partial x}1\hat{j}$$

Solve for nonzero terms $$\frac{\partial}{\partial x}\arctan \left({\frac{x}{y}}\right)=\frac{1}{y\left(1+\frac{x^2}{y^2}\right)}=\frac{y}{x^2+y^2}$$ and $$\frac{\partial}{\partial y}ln \sqrt{x^2+y^2}=\frac{1}{2}\cdot 2y \cdot\frac{1}{sqrt{x^2 + y^2}}\cdot\frac{1}{\sqrt{x^2 + y^2}}=\frac{y}{x^2 + y^2}$$

Simplify the curl $$\nabla \times F = 0\hat{i} - 0\hat{j} + \frac{\partial}{\partial x}\arctan \left({\frac{x}{y}}\right)\hat{k}+\frac{\partial}{\partial y}ln \sqrt{x^2+y^2}\hat{k}-0\hat{i}-0\hat{j}=\frac{2y}{x^2 + y^2}\hat{k}$$

Evaluate the surface integral by expressing it as a double integral over a region $$R$$.$$\int_S \int curlF \cdot N dS = \int_S \int \left(0\hat{i} + 0\hat{j} + \frac{2y}{x^2 + y^2}\hat{k}\right) \cdot \left(2\hat{i} + 3\hat{j} + 1\hat{k}\right)dS=\int_R \int\frac{2y}{x^2 + y^2}dA=\int_0^{\frac{\pi}{2}}\int_{0}^{2\sin{2\theta}}\frac{2r\sin{\theta}}{r^2}rdrd\theta$$$$    \int_{0}^{\frac{\pi}{2}}\int_{0}^{2\sin{2\theta}}2\sin{\theta}drd\theta=\int_{0}^\frac{\pi}{2}2\sin{\theta}\bigg\vert_{0}^{4\sin{\theta}\cos{theta}} d\theta$$ where $$\frac{1}{2}\sin{2\theta}=\sin{\theta}\cos{\theta}$$$$    \int_{0}^{\frac{\pi}{2}}8\sin^2{\theta}\cos{\theta}d\theta=\frac{8}{3}\sin^3{\theta} \bigg\vert^{\frac{\pi}{2}}_{0}=\frac{8}{3}$$
