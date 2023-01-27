---
layout: single
title: La criba de Eratóstenes.
excerpt: "Eratóstenes de Cirene, matemático griego, desarrollo alrededor de los años 200 a.C un algoritmo que nos permite identificar los números primos menores a un $$n$$ dado. Veremos como funciona este algoritmo, daremos un par de detaller del mismo, y por otro lado expondremos una relación entre este algoritmo y el teorema de Dirichlet."
date: 2022-02-17
classes: wide
header:
  teaser: /assets/images/la-criba-de-eratostenes/criba.gif
  teaser_home_page: true
  icon: 
categories:
  - Teoría de Números
  - Álgebra Computacional
tags:  
  - Números Primos
  - Euler
  - Eratóstenes
  - Dirichlet
  - Algoritmo
---

<center> <img src="/assets/images/la-criba-de-eratostenes/criba.gif" weidth="30%" heigth="30%"> </center>

## Introducción

Vamos a conocer la criba de **Eratóstenes**, uno de los algoritmos más conocidos para obtener y listar números primos. Además veremos su relación con el teorema de **Dirichlet**.

## Pseudocódigo

En un futuro presentaremos a qué nos referimos con esto de **Complejidad** e introduciremos la notación $$O$$ grande.

La criba de Eratóstenes (Complejidad $$O(n\log{\log{n}})$$)
----
**Entrada:**  $$n\in\mathbb{N}$$.

**Algoritmo:** 
  - Escriba todos los números naturales de $$2$$ hasta $$n$$.
  - Tache todos los múltiplos de $$2$$ hasta $$n$$ a excepción de $$2$$.
  - A continuación busque el siguiente número que no se encuentre tachado, en este caso el $$3$$, y tache todos los múltiplos de $$3$$ hasta $$n$$ a excepción de $$3$$, luego repita este mismo procedimiento hasta que el último número tachado sea menor o igual a $$\sqrt{n}$$ (la razón de esto la vimos en el post de división por tentativa #Probar si se puede dejar el hipervinculo).

**Salida:** Todos los números que no estén tachados son números primos.

## Ejemplo

Supongamos que queremos encontrar los números primos menores que $$50$$, debemos entonces aplicar el algoritmo con $$n=50$$, gráficamente el resultado debería de ser el siguiente:

$$\begin{array}{cccccc} & \texcolor{green}{2} & 3 &  \textcolor{green}{\not4} & 5 & \textcolor{green}{\not 6} \\ 7 & \textcolor{green}{\not 8} & \textcolor{blue}{\not9} & \textcolor{green}{\not10} & 11 & \textcolor{green}{\not12} \\ 13 & \textcolor{green}{\not14} & \textcolor{blue}{\not15} & \textcolor{green}{\not16} & 17 & \textcolor{green}{\not18} \\ 19 & \textcolor{green}{\not20} & \textcolor{blue}{\not21} & \textcolor{green}{\not22} & 23 & \textcolor{green}{\not24} \\ \not25 & \textcolor{green}{\not26} & \textcolor{blue}{\not27} & \textcolor{green}{\not28} & 29 &  \textcolor{green}{\not30} \\ 31 & \textcolor{green}{\not32} &  \textcolor{blue}{\not33} & \textcolor{green}{\not34} & \not35 & \textcolor{green}{\not36} \\ 37 & \textcolor{green}{\not38} &  \not39 & \textcolor{green}{\not40} & 41 & \textcolor{green}{\not42} \\ 43 & \textcolor{green}{\not44} & \textcolor{blue}{\not45} & \textcolor{green}{\not46} & 47 & \textcolor{green}{\not48} \\ \not49 & \textcolor{green}{\not50} & & & & \end{array}$$

Si verificamos el procedimiento por pasos podremos notar que el último número del cuál tomaremos múltiplos para tachar es el $$7$$, esto es justamente porque $$7\leq \sqrt{50}$$, en otras palabras, $$7^{2}=49 \leq 50$$ y el $$50$$ queda tachado al ser múltiplo de $$2$$.

Además, si somos curiosos y observamos con detenimiento la gráfica notaremos que a excepción de $$2$$ y $$3$$ todos los números primos se encuentran en la primera y quinta columna, en nuestro caso, sabemos que los números de la primera columna son de la forma $$6k+1$$ y los números de la quinta columna son de la forma $$6k+5$$.

¡Nuevamente las matemáticas nos van a demostrar que las coincidencias no existen! Veamos porqué ocurre esto.

## Teorema de Dirichlet

Si $$mcd(a,d)=1$$ (Máximo común divisor de $$a$$ y $$d$$ es igual a $$1$$) con $$a,d\in\mathbb{Z}^{+}$$, entonces hay un número infinito de primos de la forma $$a+dk$$ con $$k\in\mathbb{Z}^{+}$$.

En nuestro caso, como $$mcd(6,1)=1$$, entonces tenemos que existen infinitos números primos de la forma $$6+k$$. De la misma forma como $$mcd(6,5)=1$$, entonces tenemos que existen infinitos números primos de la forma $$6+5k$$.

Veamos de manera rápida porqué esto no ocurre para las demás columnas:

* Suponga $$p\in\mathbb{N}$$ como un número primo, luego si $$n=6+2k$$, entonces $$p=2(3+k)$$, **CONTRADICCIÓN**, ya que por hipótesis $$p$$ es un número primo.

* Suponga $$p\in\mathbb{N}$$ como un número primo, luego si $$n=6+3k$$, entonces $$p=3(2+k)$$, **CONTRADICCIÓN**, ya que por hipótesis $$p$$ es un número primo.

* Suponga $$p\in\mathbb{N}$$ como un número primo, luego si $$n=6+4k$$, entonces $$p=2(3+2k)$$, **CONTRADICCIÓN**, ya que por hipótesis $$p$$ es un número primo.

* Suponga $$p\in\mathbb{N}$$ como un número primo, luego si $$n=6+6k$$, entonces $$p=6(1+k)$$, **CONTRADICCIÓN**, ya que por hipótesis $$p$$ es un número primo.

Esto es equivalente a demostrar que todo número primo mayor o igual que $$5$$ es de la forma $$6k+1$$ o de la forma $$6k+5$$, siendo esta la misma razón por la cuál los números primos aparecen en estas columnas. Por otro lado, este resultado se puede probar adaptando una demostración de **Euclides**, pero hemos visto como el teorema de **Dirichlet** generaliza esta situación.