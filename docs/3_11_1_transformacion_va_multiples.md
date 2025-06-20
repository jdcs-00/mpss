<!--
---------------------------------
PRESENTACIÓN DE CLASE
 
Universidad de Costa Rica  
Escuela de Ingeniería Eléctrica  
IE0405 - Modelos Probabilísticos de Señales y Sistemas  
---------------------------------
-->

<!--
---------------------------------
PRESENTACIÓN DE CLASe

Universidad de Costa Rica
Escuela de Ingeniería Eléctrica
IE0405 - Modelos Probabilísticos de Señales y Sistemas
---------------------------------
-->

# Transformaciones de  
# variables aleatorias múltiples

---

Similar al caso de las variables aleatorias marginales, es posible “transformar” dos o más variables aleatorias conjuntas mediante funciones, y el objetivo es encontrar la función de densidad de las nuevas variables aleatorias conjuntas.

---

## Transformaciones de variables aleatorias múltiples

> Considérese el caso de hallar la densidad conjunta para un conjunto de nuevas variables aleatorias $Y_i$:  
> 
> $$
> Y_i = T_i(X_1, X_2, \ldots, X_N) \qquad i = 1, 2, \ldots, N
> $$
> 
> definidas por transformaciones funcionales $T_i$.

**Nota**: $X_i$ puede ser continua, discreta o mixta, mientras las funciones $T_i$ pueden ser lineales o no, continuas, segmentadas, etcétera.

---

- Las nuevas variables aleatorias $Y_i$ son producidas por funciones **univaluadas** continuas $T_i$ con derivadas parciales continuas en todas partes.
- Existe un conjunto de funciones inversas continuas $T_{j}^{-1}$ tal que las variables originales puedan expresarse como funciones continuas univaluadas de las variables nuevas:

$$
X_j = T_{j}^{-1}(Y_1, Y_2, \ldots, Y_N) \qquad j = 1, 2, \ldots, N
$$

Estas suposiciones implican que un punto en el espacio de muestras conjunto de las $X_i$ mapea en un solo punto en el espacio de las nuevas variables $Y_j$.

---

## Premisa de la relación entre $X_i$ e $Y_i$

- Sea $\mathcal{R}_X$ una región cerrada de puntos en el espacio de las $X_i$, y $\mathcal{R}_Y$ sea la región correspondiente de puntos mapeados en el espacio de las $Y_j$.
- Entonces, **la probabilidad de que un punto caiga en $\mathcal{R}_X$ iguala a la probabilidad de que su punto mapeado caiga en $\mathcal{R}_Y$**.

Estas probabilidades, en términos de densidades conjuntas, son:

$$

\int \cdots \int_{\mathcal{R}_X}
  f_{X_1,\dots,X_N}(x_1,\dots,x_N)\;dx_1\cdots dx_N
=\ 
\int \cdots \int_{\mathcal{R}_Y}
  f_{Y_1,\dots,Y_N}(y_1,\dots,y_N)\;dy_1\cdots dy_N

$$
---

## Resolver para $f_{Y_1, \ldots, Y_N}(y_1, \ldots, y_N)$

La ecuación anterior puede resolverse tratándola como una integral múltiple donde se hace un cambio de variables.

- Las variables $x_i$ se cambian a nuevas variables $y_i$ mediante la transformación.
- Los límites cambian de la región $\mathcal{R}_X$ a la región $\mathcal{R}_Y$.
- Finalmente, el diferencial de volumen $\mathrm{d}x_1 \cdots \mathrm{d}x_N$ cambiará a $\vert J\vert \, \mathrm{d}y_1 \cdots \mathrm{d}y_N$, donde $\vert J \vert$ es el jacobiano de las transformaciones.

![Imagen](images/11_matrices.svg)

---

El lado izquierdo de la ecuación se convierte en:

$$

\begin{aligned}
  &\underbrace{\int \cdots \int}_{\text{sobre }\mathcal{R}_X}
  f_{X_1, \ldots, X_N}(x_1, \ldots, x_N)
  \, dx_1 \cdots dx_N
  \\
  &\qquad=
  \underbrace{\int \cdots \int}_{\text{sobre }\mathcal{R}_Y}
  f_{X_1, \ldots, X_N}\big(x_1 = T_{1}^{-1}, \ldots, x_N = T_N^{-1}\big)
  \left| J \right|
  \, dy_1 \cdots dy_N
\end{aligned}

$$


> Dado que este resultado debe igualar el lado derecho, entonces:
>
> $$
> f_{Y_1, \ldots, Y_N}(y_1, \ldots, y_N) = f_{X_1, \ldots,X_N}(x_1 = T_{1}^{-1}, \ldots,x_N = T_{N}^{-1})\vert J\vert
> $$

---

### **Nota sobre el jacobiano**


>El jacobiano es el determinante de una matriz de derivadas parciales, definido por:
>
>$$
J = \left|
\begin{array}{ccc}
  \dfrac{\partial T_{1}^{-1}}{\partial Y_1} & \cdots & \dfrac{\partial T_{1}^{-1}}{\partial Y_N} \\
  \vdots & \ddots & \vdots \\
  \dfrac{\partial T_{N}^{-1}}{\partial Y_1} & \cdots & \dfrac{\partial T_{N}^{-1}}{\partial Y_N}
\end{array}
\right|
=
\mathsf{det} \left(
\begin{array}{ccc}
  \dfrac{\partial T_{1}^{-1}}{\partial Y_1} & \cdots & \dfrac{\partial T_{1}^{-1}}{\partial Y_N} \\
  \vdots & \ddots & \vdots \\
  \dfrac{\partial T_{N}^{-1}}{\partial Y_1} & \cdots & \dfrac{\partial T_{N}^{-1}}{\partial Y_N}
\end{array}
\right)
$$


---

## Caso especial: dos funciones de dos variables aleatorias

Dada una densidad conjunta $f_{X,Y}(x,y)$ de dos variables aleatorias, y dos funciones

$$
Z = g(X,Y) \quad \text{y} \quad W = h(X,Y)
$$

Queremos encontrar la densidad conjunta $f_{Z,W}(z,w)$.

Igual que antes:

- Si $g(X,Y)$ y $h(X,Y)$ son continuas y diferenciables, es posible desarrollar una forma de obtener el pdf directamente.
- Para derivar el resultado anterior, se asume que $g(X,Y)$ y $h(X,Y)$ son transformaciones uno a uno, de forma que su inversa existe, aquí definidas como

$$
X \triangleq P(Z,W) \quad \text{y} \quad Y \triangleq Q(Z,W)
$$

---

## Dos funciones de dos variables aleatorias

En el plano $zw$ la región de interés está definida por un rectángulo de lados $\Delta z$ y $\Delta w$.

<p align="center">
  <img src="images/11_deltaz_deltaw.svg" width="70%">
</p>

- Si $\Delta z$ y $\Delta w$ son suficientemente pequeños, se puede aproximar la siguiente probabilidad $P(\cdot)$:


$$
P\left[ (Z,W) \in \Delta z \Delta w \right] \approx f_{Z,W}(z,w) \cdot \Delta z \Delta w
$$

**Nota**: recordar la interpretación de la probabilidad conjunta como el volumen debajo de la curva bidimensional de $f_{X,Y}(x,y)$. En este caso sería “base por altura”.

---

Esta área se mapea mediante las transformaciones $x = P(z,w)$ y $y = Q(z,w)$ a una nueva área $\Delta$ en el plano $xy$.  
Debido al mapeo entre $(X,Y)$ y $(Z,W)$, lo anterior debe ser igual a:

$$
P\left( (X,Y) \in \Delta \right) \approx f_{X,Y}(x = P(z,w), y = Q(z,w)) \cdot \Delta
$$


- ¿Cómo relacionar entonces las áreas $\Delta z \Delta w$ y $\Delta$?  
  Igualando el área de un rectángulo con el de un paralelogramo, se puede demostrar (https://youtu.be/rnnrUDdKzm0) que:

$$
\Delta = \vert J \vert \, \Delta z \, \Delta w
$$

---

donde

$$
J(z,w) \triangleq \frac{\partial (P,Q)}{\partial(z,w)} = \det 
\begin{pmatrix}
\frac{\partial P}{\partial z} & \frac{\partial P}{\partial w} \\
\frac{\partial Q}{\partial z} & \frac{\partial Q}{\partial w}
\end{pmatrix}
$$

y se le llama "el jacobiano de la transformación $(P,Q)$".

> Así entonces:
>
> $$
> f_{Z,W}(z,w) = f_{X,Y} \left[ x = P(z,w), y = Q(z,w) \right] \vert J \vert
> $$

Comparar con:

$$
f_{Y_1, \ldots, Y_N}(y_1, \ldots, y_N) = f_{X_1, \ldots,X_N}(x_1 = T_{1}^{-1}, \ldots,x_N = T_{N}^{-1})\vert J\vert
$$
