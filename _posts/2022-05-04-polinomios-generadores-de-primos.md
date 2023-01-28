---
layout: single
title: Polinomios generadores de primos.
excerpt: "Pendiente jejeje :3."
date: 2022-05-04 
classes: wide
header:
  teaser: /assets/images/la-criba-de-eratostenes/criba.gif
  teaser_home_page: true
  icon: 
categories:
  - X
tags:  
  - X
---

Los números primos han sido objeto de estudio de los matemáticos por siglos, hoy veremos varias de las fórmulas que generan números primos, centrándonos particularmente en el caso de los polinomios y veremos por qué es imposible que un polinomio no constante, de una variable evaluado en los enteros nos de siempre un número primo.

Quizás el polinomio generador de primos más popular es el siguiente:

$$n^2-n+41$$

Este polinomio fue dado por **Euler** en $$1772$$ y nos genera $$40$$ primos diferentes evaluándolo entre $$0$$ y $$40$$, sobre este polinomio podemos encontrar muchas variantes, una de las mejores se encuentra en el libro *An introduction to theory of numbers - G.H Hardy y E.M Wright*

$$n^2-79n+1601=(n-40)^2+(n-40)+41$$

Este polinomio ya nos genera primos entre $$0$$ y $$79$$, a continuación veremos una lista de unos cuantos polinomios generadores de primos:

$$
\begin{align*}
n^4-97n^3+3294n^2-45458n+213589& &&\rightarrow 49 \\
36n^2-810n+2753& &&\rightarrow 45 \\
2n^2+29& &&\rightarrow 29 \\
n^2+n+17& &&\rightarrow 16 \\
\end{align*}
$$

Estos polinomios nos generan $$49,45,29$$ y $$16$$ números primos, en cada caso.

Pero los polinomios no son la única forma de obtener números primos, por ejemplo tenemos la siguiente expresión:

$$a(n)= \rfloor \dfrac{Res(n!,n+1)}{n}\lfloor (n-1) + 2$$

Donde $$Res(n!,n+1)$$ denota el resto de la división entera entre $$n!$$ y $$n+1$$, esta expresión genera números primos para todo entero positivo $$n$$, el problema es que tiene un gran costo computacional porque implica el cálculo de un factorial. Siendo así, buscar polinomios o expresiones diferentes que nos generen primos es una gran solución para disminuir la complejidad del cálculo. Por otro lado, es imposible que un polinomio con coeficientes enteros, de una variable y entrada en los enteros nos genere siempre números primos, ya que:

## Teorema

Sea $$p(x)=c_nX^n+c_{n-1}x^{n-1}+\cdots+c_1x+c_0$$ un polinomio de coeficientes enteros, entonces $$p(n)$$ es compuesto para infinitos valores del entero $$n$$.

## Demostración

Supongamos que existe un entero $$n_{0} \geq 1$$ tal que $$p(n_{0})=q$$ con $$q$$

$$p(n_0+qh)=p(n_0)+Cq=q+Cq=q(1+C)$$

Donde $$C$$ es un entero, por tanto $$p(n_0+qh)$$ es compuesto para todo $$h$$ tal que $$n_0+qh \geq n_1$$, como hay infinitos valores de $$h$$ que cumplen la condición, entonces queda demostrada la afirmación.

$$\blacksquare$$





