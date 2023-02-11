---
layout: single
title: Notación O Grande
excerpt: "Encontrar algoritmos eficientes para hacer todo tipo de tareas es algo muy complicado y a esto se dedican muchos matemáticos. Así mismo es importante entender que tanto tiempo u operaciones deben realizar nuestros algoritmos para realizar distintas tareas, por consiguiente la notación O grande es importante de entender, ya que esta nos permitirá acotar el tiempo de ejecución de nuestro algoritmo para algún $$n$$ arbitrario." 
date: 2022-12-08
classes: wide
header:
  teaser: /assets/images/residuos-cuadraticos/legendre.jpg  
  teaser_home_page: true
  icon: 
categories:
  - Álgebra Computacional
tags:  
  - Algoritmo
---

Hoy veremos una forma de analizar nuestros algoritmos en cualquier lenguaje de programación:

## Notación O Grande:


<center><script type="text/tikz">



\tikzset{every picture/.style={line width=0.75pt}} %set default line width to 0.75pt        

\begin{tikzpicture}[x=0.75pt,y=0.75pt,yscale=-1,xscale=1]
%uncomment if require: \path (0,472); %set diagram left start at 0, and has height of 472

%Shape: Axis 2D [id:dp11483536320529097] 
\draw [color={rgb, 255:red, 255; green, 255; blue, 255 }  ,draw opacity=1 ][line width=1.5]  (13.57,389.79) -- (623.57,389.79)(74.57,16.29) -- (74.57,431.29) (616.57,384.79) -- (623.57,389.79) -- (616.57,394.79) (69.57,23.29) -- (74.57,16.29) -- (79.57,23.29)  ;
%Shape: Grid [id:dp5849393120179278] 
\draw  [draw opacity=0][dash pattern={on 1.69pt off 2.76pt}][line width=1.5]  (74.57,44.58) -- (607.26,44.58) -- (607.26,390.8) -- (74.57,390.8) -- cycle ; \draw  [color={rgb, 255:red, 255; green, 255; blue, 255 }  ,draw opacity=1 ][dash pattern={on 1.69pt off 2.76pt}][line width=1.5]  (74.57,44.58) -- (74.57,390.8)(138.41,44.58) -- (138.41,390.8)(202.26,44.58) -- (202.26,390.8)(266.1,44.58) -- (266.1,390.8)(329.94,44.58) -- (329.94,390.8)(393.78,44.58) -- (393.78,390.8)(457.62,44.58) -- (457.62,390.8)(521.47,44.58) -- (521.47,390.8)(585.31,44.58) -- (585.31,390.8) ; \draw  [color={rgb, 255:red, 255; green, 255; blue, 255 }  ,draw opacity=1 ][dash pattern={on 1.69pt off 2.76pt}][line width=1.5]  (74.57,44.58) -- (607.26,44.58)(74.57,108.43) -- (607.26,108.43)(74.57,172.27) -- (607.26,172.27)(74.57,236.11) -- (607.26,236.11)(74.57,299.95) -- (607.26,299.95)(74.57,363.79) -- (607.26,363.79) ; \draw  [color={rgb, 255:red, 255; green, 255; blue, 255 }  ,draw opacity=1 ][dash pattern={on 1.69pt off 2.76pt}][line width=1.5]   ;
%Curve Lines [id:da31886486777884215] 
\draw [color={rgb, 255:red, 255; green, 0; blue, 0 }  ,draw opacity=1 ][line width=1.5]    (74.57,283.57) .. controls (98.87,265.31) and (115.68,141.04) .. (180.58,230.46) .. controls (245.48,319.89) and (248.01,311.93) .. (264.02,309.6) .. controls (280.04,307.27) and (295.97,262.73) .. (332.36,233.55) .. controls (368.74,204.37) and (385.61,130.1) .. (414.21,187.12) .. controls (442.81,244.13) and (478.79,142.48) .. (500.09,153.97) .. controls (521.39,165.47) and (582.82,152.36) .. (589.65,147.23) ;
%Curve Lines [id:da08176059116499501] 
\draw [color={rgb, 255:red, 255; green, 255; blue, 255 }  ,draw opacity=1 ][line width=1.5]    (73.57,203.91) .. controls (97.87,185.65) and (114.68,61.38) .. (179.58,150.8) .. controls (244.48,240.22) and (267.45,195.97) .. (287.76,198.62) .. controls (308.08,201.28) and (316.51,331.01) .. (365.09,283.57) .. controls (413.67,236.13) and (381.46,172.9) .. (418.1,177.35) .. controls (454.73,181.81) and (475.72,236.43) .. (509.57,261.29) .. controls (543.42,286.14) and (596,299.97) .. (603.57,294.29) ;

% Text Node
\draw (449,397) node [anchor=north west][inner sep=0.75pt]  [color={rgb, 255:red, 255; green, 255; blue, 255 }  ,opacity=1 ,xscale=1.3,yscale=1.3] [align=left] {$\displaystyle b$};
% Text Node
\draw (597,133) node [anchor=north west][inner sep=0.75pt]  [color={rgb, 255:red, 255; green, 255; blue, 255 }  ,opacity=1 ,xscale=1.3,yscale=1.3] [align=left] {$\displaystyle c|g( x) |$};
% Text Node
\draw (612,301) node [anchor=north west][inner sep=0.75pt]  [color={rgb, 255:red, 255; green, 255; blue, 255 }  ,opacity=1 ,xscale=1.3,yscale=1.3] [align=left] {$\displaystyle f( x)$};


\end{tikzpicture}

</script>
</center>

Comencemos con una definición

## Definición:

Sea $$g(x)$$ una función de variable real definida para todo real no negativo. Denotamos por $$O(g(x))$$, leído como O grande de $$g$$, el conjunto

$$\begin{aligned}
  O(g(x))& =\{f(n): \text{ existen reales} c>0 \text{ y } b \geq 0 \text{ tales que}\\
  & \quad |f(x)| \leq c|g(x)|, \text { para todo } x \geq b\}
\end{aligned}$$

## Pero, ¿y esto de qué nos sirve?

Básicamente podemos analizar nuestros algoritmos y contar las operaciones que hacen en cada una de las iteraciones, de esta forma obtener una función $$g(x)$$ y con $$O(g(x))$$ podemos ver el crecimiento de la misma comparado con otras funciones

## ¿Y esto qué nos dice de nuestro algoritmo?

Nos dice que qué tanto le tomará darnos un resultado dependiendo del tamaño de la tarea que le asignemos

No es lo mismo para un computador multiplicar 2 números de 100 dígitos que dos de 4 millones de dígitos, entonces la velocidad en la que nos entregue el resultado depende enteramente de nuestra capacidad de desarrollar algoritmos eficientes.

En la publicación de "División por tentativa" vimos como al implementar un pequeño teorema en teoría de números ahorramos mucho tiempo en factorizar un número por ejemplo.

## Ejemplo:

Si $$f(n)=n^2+10^{10} n$$, entonces $$f=O\left(n^2\right)$$. En efecto,

$$
\begin{aligned}
& |f(n)|=\left|n^2+10^{10} n\right| \\
& \leq n^2+10^{10} n \quad(n \geq 0) \\
& \leq n^2+10^{10} n^2 \quad(n \geq 1) \\
& =\left(10^{10}+1\right) n^2=c\left|n^2\right| \text {, } \\
\end{aligned}
$$

con $$c=10^{10}+1$$

Require: $$n \in \mathbb{Z}$$

1: procedure ALGEJER2

$\begin{array}{lc}2: & \text { for } i:=1 \text { to } n \text { do } \\ 3: & \text { for } j:=1 \text { to } i \text { do } \\ 4: & \text { for } k:=1 \text { to } j \text { do } \\ 5: & x:=i \cdot j \cdot k \\ 6: & \text { end for } \\ 7: & \text { end for } \\ 8: & \text { end for } \\ 9: & \text { end procedure }\end{array}$

Este algoritmo por ejemplo hace dos multiplicaciones para calcular el producto de 3 enteros y tiene 3 for anidados.

Notemos que el primer for va acumulando las operaciones que se hacen en los 2 de adentro, el último for ejecuta las 2 operaciones, luego para el segundo sumamos estas operaciones que se van acumulando y obtenemos:

$$
\sum_{m=1}^i 2 m=i(i+1)
$$

Como dijimos el primer for suma estas operaciones luego el total de operaciones que hace el algoritmo es:

$$
\sum_{i=1}^n i(i+1)=\frac{n(n+1)(n+2)}{2}
$$

al multiplicar los términos nos damos cuenta que el algoritmo es $$O\left(n^3\right)$$ (o de orden cúbico)

Note que esto es un abuso de notación tremendo, pero lo importante es que sirve $x d$, ahora veamos el tiempo computacional.

Asumiendo que una operación toma un nanosegundo ( $$10^{-9}$$ segundo), comparamos el tiempo computacional para diferentes ordenes de una función $$f(n)$$ a continuación.

$$
\begin{array}{|c||c|c|c|c|}
\hline f(n) & n=10 & n=10^3 & n=10^5 & n=10^7 \\
\hline \log _2(n) & 3,3 * 10^{-9} \mathrm{~s} & 10^{-8} \mathrm{~s} & 1,7 * 10^{-8} \mathrm{~s} & 2,3 * 10^{-8} \mathrm{~s} \\
n & 10^{-8} \mathrm{~s} & 10^{-6} \mathrm{~s} & 0,0001 \mathrm{~s} & 0,01 \mathrm{~s} \\
n \log _2(n) & 3,3 * 10^{-8} \mathrm{~s} & 0,000010 \mathrm{~s} & 0,0017 \mathrm{~s} & 0,23 \mathrm{~s} \\
n^2 & 10^{-7} \mathrm{~s} & 0,0010 \mathrm{~s} & 10 \mathrm{~s} & 27 \text { horas } \\
n^3 & 10^{-6} \mathrm{~s} & 1 \mathrm{~s} & 11,5 \text { días } & 31709 \text { años } \\
2^n & 10^{-6} \mathrm{~s} & - & - & - \\
\hline
\end{array}
$$

Luego el orden logaritmico sería lo más ideal si queremos que nuestros programas compilen rápido y el exponencial el peor, para tareas pesadas nos podemos morir sin conocer el resultado.