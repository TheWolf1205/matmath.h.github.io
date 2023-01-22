---
layout: single
title: División por tentativa
excerpt: "Leonhard Euler demostró aproximadamente en 1772 que 2.147.483.647 es un numero primo y le mando una carta a Daniel Bernoulli informandole de su prueba, ¿Cómo fue que lo hizo con las limitaciones de su epoca para realizar cálculos?"
date: 2022-01-24
classes: wide
header:
  teaser: /assets/images/division-por-tentativa/euler.jpeg
  teaser_home_page: true
  icon: /assets/images/hackthebox.webp
categories:
  - Teoría de Números
  - Álgebra Computacional
tags:  
  - Numeros de Mersenne
  - Numeros Primos
  - Euler
---

<center> <img src="/assets/images/division-por-tentativa/euler.jpeg"> </center>
<br>

Un número primo $$n$$ es un entero que solo es divisible por $$2$$ números distintos, siendo estos $$1$$ y $$n$$, entonces, si queremos verificar si un número $$n$$ es primo, debemos comprobar que no tiene algún factor primo $$k$$ tal que $$1<k<n$$, lo cual puede ser una tarea tediosa y larga. Así, a continuación presentaremos un teorema que nos ayudará a ahorrar tiempo a la hora de verificar si un número $$n$$ es primo, siendo este el mismo que usó **Euler** en su demostración.

## Teorema
Sea $$n\in\mathbb{Z}$$, si $$n$$ es compuesto, entonces $$n$$ tiene un factor primo $$k$$ menor o igual a $$\sqrt{n}$$.

## Demostración.

Sea $$n$$ un compuesto (positivo), entonces existen a y $$b \in \mathbb{Z}$$ tales que $$n=a b$$, con $$1<a, b<n$$. Por tricotomía podemos suponer que $$a \leq b$$, sin pérdida de generalidad.

Veamos que $$a \leq \sqrt{n}$$ (lo que queremos demostrar), de lo contrario $$\sqrt{n}<a \leq b$$ así $$n=a \cdot b \geq a \cdot a>\sqrt{n} \cdot \sqrt{n}=n$$, es decir que $n>n$, **CONTRADICCIÓN**, entonces queda demostrado que $n$ tiene un factor $$a \leq \sqrt{n}$$, pero aún tenemos que verificar si es primo.

Ahora si a es primo pues ya acabamos, así que consideremos el otro caso, si $a$ no es primo, como $$a>1$$, entonces por el Teorema Fundamental de la Aritmética a tiene un factor primo que lo divide y por transitividad también divide a $$n$$, que es justamente lo que se quería demostrar.

$$\blacksquare$$

Este teorema es muy utíl, ya que su contrarecíproco nos asegura que si $$n$$ no tiene un factor primo $$k$$ menor o igual a $$\sqrt{n}$$, entonces $$n$$ es un número primo.

Algo interesante que podemos hacer es construir un programa que verifique la primalidad de un número dividiendolo entre los $$n$$ números menores que él y verificando el resultado, claramente este algoritmo no será muy eficiente, pero lo bueno es que es sencillo de programar y nos puede arrojar una gran diferencia de tiempo empleado si usamos o no el teorema anterior.

## Imágenes de comparación.

La imagen de la izquierda muestra el tiempo empleado por el programa para verificar la primalidad de $$2.147.483.647$$ usando el teorema y la de la derecha no la utiliza.

## Algoritmo C++


**Euler** Utilizó este resultado para verificar que el número $$2.147.483.647$$ es primo y mejoró el método de **Cataldi**, por lo que solo tuvo que verificar $$372$$ divisiones.

Curiosamente $$2.147.483.647 = 2^{(2^{5}-1)}-1$$ lo que lo convierte en un primo doble de **Mersenne**, además a continuación mencionaremos otro par de curiosidades sobre este número.

Durante diciembre de **2014** cuando el vídeo que hizo famoso a **PSY, “Gangnam Style”**, llegó a las $$2.147.483.647$$ views y el sistema de $$32-bit$$ de la web de vídeos no pudo continuar contándolas porque simplemente había llegado a su máximo. 

El 4 de junio de **1996** despegó el primer vuelo del cohete **Ariane 5** manejado por la Agencia Espacial Europea. Dentro de él no había una tripulación pero sí estaba cargado con cuatro satélites científicos muy costosos. El vuelo explotó apenas 39 segundos después de despegar, perdiendo alrededor de **370 millones de dólares**. Después de un poco de investigación se dieron cuenta que el problema no era más que un bug de software que involucraba el número $$2.147.483.647$$. Aparentemente, Ariane 5 necesitaba una aceleración horizontal mayor que los modelos previos porque su trayecto era distinto, y esto hizo que todos los computadores que controlaban el auto-piloto se confundieran y que comenzara una secuencia para auto-destruirse. 
