---
layout: single
title: Residuos cuadráticos
excerpt: "En álgebra se estudian detalladamente las soluciones de ecuaciones polinómicas, de forma análoga aquí estudiaremos las congruencias polinómicas con coeficientes en los enteros" 
date: 2022-09-18
classes: wide
header:
  teaser: /assets/images/residuos-cuadraticos/legendre.jpg  
  teaser_home_page: true
  icon: 
categories:
  - Teoría de Números
  - Álgebra
tags:  
  - Ecuaciones diofánticas
  - Congruencias
  - Teoría de números
---

En álgebra se estudian detalladamente las soluciones de ecuaciones polinómicas, de forma análoga aquí estudiaremos las congruencias polinómicas con coeficientes en $$\mathbb{Z}$$.

La congruencia $$f(x) \equiv 0$$ (mód $$n$$ ) se llama lineal cuando $$f(x)$$ es un polinomio de grado 1.

Consideraremos solo las soluciones de la ecuación que sean incongruentes, es decir que tengan un residuo distinto módulo $$n$$

Toda congruencia lineal se puede escribir de la forma $$a x \equiv b \pmod n$$

Tenemos el siguiente teorema que no es difícil de verificar

## Teorema:

La congruencia lineal $$a x \equiv b($$ mód $$n)$$ tiene solución si $$y$$ solo si $$d \mid b$$, donde $$d=(a, n)$$

## Congruencias cuadráticas módulo $$p$$:

Una congruencia cuadrática con módulo primo $$p$$ tiene la forma,

$$
a x^2+b x+c \equiv 0(\operatorname{mód} p), \text { con } \operatorname{mcd}(a, p)=1
$$

Note que $$\operatorname{mcd}(4 a, p)=1$$, luego la congruencia anterior es equivalente a:

$$
4 a^2 x^2+4 a b x+4 a c \equiv 0(\operatorname{mód} p)
$$

Y por tanto a la siguiente: