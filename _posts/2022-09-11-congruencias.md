---
layout: single
title: Congruencias
excerpt: "Aquí veremos una introducción a la aritmética modular y su fundamentación con base a las congruencias, definiremos estos conceptos y veremos un par de resultadosS" 
date: 2022-09-11 
classes: wide
header:
  teaser: /assets/images/congruencias/clock.png
  teaser_home_page: true
  icon: 
categories:
  - Teoría de números
  - Álgebra
tags:  
  - Ecuaciones diofánticas
  - Congruencias
  - Teoría de números
---

## Definición:

Sean $$a$$ y $$b$$ enteros cualesquiera y $$n$$ un entero positivo. Si $$n \mid(a-b)$$ (n divide a $$(a-b)$$ ), decimos que a y $$b$$ son congruentes módulo $n$ y lo denotamos por

$$
a \equiv b(\bmod n)
$$

Si a no es congruente con $$b$$ módulo $$n$$, escribimos $$ a \not \equiv b(\bmod n)$$

Denotaremos por $$\operatorname{Res}(a, b)$$ el residuo de dividir a entre b.

Note que dos enteros $$a$$ y $$b$$ son congruentes módulo $$n$$ si y solo si tienen el mismo residuo al ser divididos por $$n$$.

Algo a tener en cuenta es que la congruencia es una relación de equivalencia, es decir, es transitiva, simétrica y reflexiva, ahora veamos unos cuantos teoremas que no son difíciles de verificar usando la definición de congruencia.

## Teorema:

Si $$a \equiv b(\bmod n)$$ y $$c \equiv d(\bmod n)$$ entonces

* Para todo par de enteros $$r$$ y $$s, a r+c s \equiv b r+d s(\bmod$$
n).

* $$a+c \equiv b+d(\bmod n)$$.
  
* $$a-c \equiv b-d(\bmod n)$$.
  
* $$a c \equiv b d(\bmod n)$$.
  
* Para todo entero positivo $$k, a^k \equiv b^k(\bmod n)$$.

* Para todo entero $$r, a+r \equiv b+r(\bmod n)$$.
  
* Para todo entero $$r, a r \equiv b r(\bmod n)$$.
  
Veremos la demostración de una de estas afirmaciones, las demás se hacen de forma similar por lo cual puede ser un buen ejercicio hacerlas.

## Demostración:

Si $$a \equiv b(\bmod n)$$, entonces $$n \mid(a-b)$$, es decir, existe $$k \in \mathbb{Z} a-b=k \cdot n$$, además como $$c \equiv d(\bmod n)$$, existe $$f \in \mathbb{Z}$$ tal que $$c-d=n \cdot f$$

Luego sumando estas igualdades tenemos que

$$
\begin{aligned}
0 & =c-d-n \cdot f+a-b-k \cdot n \\
& =c-d+a-b-n \cdot(k+f)
\end{aligned}
$$

Por tanto $$(c+a)-(b+d)=n \cdot(k+f)$$, luego por la propiedad clausurativa de la suma en los enteros, $$k+f \in$ $\mathbb{Z}$$, luego $$a+c \equiv b+d(\bmod n)$$

$$\tag*{$\blacksquare$}$$

De manera similar se hacen las demás pruebas del teorema.

