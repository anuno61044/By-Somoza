# Combinatoria 5

## Temas:
1. **Recurrencia lineal homogénea**
2. **Recurrencia lineal no homogénea**

## Recurrencia homogénea
Se dice que una recurrencia lineal es homogénea  de orden $k$ si existen $c_1,c_2,\dots c_k \in \R$ y valores iniciales para $a_1,a_2,\dots,a_k$ tal que $a_n = c_1a_{n-1} + c_2a_{n-2} + \cdots + c_ka_{n-k}$

Analicemos con orden 2 la receta para a partir de una fórmula de recurrencia hallar su forma cerrada, luego esto se puede hacer para orden $k$.

### Ecuación característica
Sea $q \ne 0 \in \R$. La sucesión $q^n$ satisface la recurrencia $a_n = c_1a_{n-1} + c_2a_{n-2} \iff q$ es raíz de $x^2 - c_1x - c_2 = 0$ la cual es conocida como ecuación característica de la recurrencia.

### `Por qué funciona?`
Si evaluamos $q^n$ en la recurrencia tenemos que $q^n = c_1q^{n-1} + c_2q^{n-2}$, luego, al dividir por $q^{n-2}$ y llevar todo al miembro izquierdo resulta en $q^2 - c_1q - c_2 = 0$ lo cual $q$ cumple por ser solución de la ecuación característica.

### Generar infinitas soluciones
Si $q$ y $p$ son soluciones de la recurrencia $\implies Aq + Bp$ es solución para cualquier $A,B \in R$, lo cual simpre genera una solución y genera infinitas soluciones, pero, serán todas?

### `Todas las soluciones son generadas`
Vamos a probar que toda solución de la recurrencia puede ser expresada como combinación lineal de las soluciones de la ecuación característica si $q$ y $p$

$$
\begin{align*}
Aq   + Bp   = a_1 \\
Aq^2 + Bp^2 = a_2
\end{align*}
$$

Para que este sistema tenga solución el siguiente determinante debe ser distinto de cero, lo cual se cumple porque $q \ne p$
$$
\begin{vmatrix}
q   & p  \\
q^2 & p^2
\end{vmatrix}
\ne 0
$$

Pero que ocurriría si la solución de la ecuación característica es doble? En ese caso una solución es $q^n$ y otra es $nq^n$. Vamos a probar que esta última es solución evaluando en la recurrencia, por Vietta tenemos que se cumple lo siguiente:

$$
\begin{aligned}
    x^2 -c_1x - c_2 = 0 \\
\end{aligned}
$$

Como $q$ es raíz doble entonces:
$$
\begin{aligned}
    x_1 + x_2 = c_1 = 2q \\
    -x_1x_2 = c_2 = -q^2
\end{aligned}
$$

Y por tanto, al evaluar en la recurrencia resulta:

$$
\begin{aligned}
nq^n = 2q(n-1)q^{n-1} -q^2(n-2)q^{n-2}
\end{aligned}
$$

Lo cual al realizar las multiplicaciones y reducir términos semejantes resulta en la igualdad.

Vamos a probar que toda solución de la recurrencia puede ser expresada como combinación lineal de las soluciones $q^n$ y $nq^n$

$$
\begin{align*}
Aq   + Bq   = a_1 \\
Aq^2 + B2q^2 = a_2
\end{align*}
$$ 

Para que este sistema tenga solución el siguiente determinante debe ser distinto de cero, lo cual se cumple porque $q \ne 0$
$$
\begin{vmatrix}
q   & p  \\
q^2 & 2q^2
\end{vmatrix}
= q^3 \ne 0
$$

### Forma genérica
Sea la relación de recurrencia 
$$a_n = c_1a_{n-1} + c_2a_{n-2} + \ldots + c_ka_{n-k}$$ 

Cuya ecuación característica es:
$$x^k - c_1x^{k-1} - \cdots - c_k = 0$$

Si esta tiene $k$ reíces distintas la solución es de la forma:
$$A_1q_1^n + A_2q_2^n + \cdots + A_kq_k^n$$

Si existe una raíz $q_r$ con multiplicidad $t$ entonces esta produce las soluciones $q_r^n, nq_r^n, n^2q_r^n, \ldots, n^{t-1}q_r^n$

## Recurrencia no homogénea
Sea $P_n$ una solución particular de la recurrencia $a_n = c_1a_{n-1} + \ldots + c_ka_{n-k} + f(n)$ entonces la solución general es $P_n + H_n$ donde $H_n$ es una solución de la homogénea.

Si el término no homogéneo de la recurrencia es de la forma $p(n)s^n$ donde $p(n)$ es un polinomio de grado $r$ y $s$ es constante hay que analizar los siguientes casos:
1. Si $s$ no es raíz de la ecuación característica hay una solución $q(n)s^n$ donde $q(n)$ tiene a lo sumo grado $r$, el cual, comienza genérico y se obtiene el valor de los coeficientes evaluándolo en la recurrencia, reduciendo términos semejantes e igualándolos.
2. Si $s$ es raíz de multiplicidad $t$ hay una solución $n^tq(n)s^n$ donde $q$ tiene grado a lo sumo $r$, aplicando luego el mismo procedimiento que el caso anterior.

Si el término no homogéneo de la recurrencia es de la forma $p_1(n)s_1^n + \cdots p_m(n)s_m^n$ entonces hay una solución particular de la forma $f_1(n) + \cdots + f_m(n)$ donde $f_i(n)$ es una solución particular de $a_n = c_1a_{n-1} + \cdots + c_ka_{n-k} + P_i(n)s_i^n$

## Ejercicios

### `Problema 1`
> Encuentre la forma cerrada de las siguientes recurrencias:
> 1. $a_n = 5a_{n-1} + 8 - 6a_{n-2}$ con $a_0=1$, $a_1=2$
> 2. $a_n = 2a_{n-1} - a_{n-2} + 4*3^n + 4$ con $a_0=10$, $a_1=35$

### `Solución`

### `Problema 2`
> Determine el número de cadenas sobre el alfabeto $\{a,b,c,d\}$ tal que todas las $a$ aparezcan antes que las $b$.

### `Solución`

### `Problema 3`
> Prueba que $\forall a \in \Z$ y $b,n \in \Z_+^*$ se cumple que la siguiente expresión es entera siempre que $4 \div (b-a^2)$
> $$\frac{1}{\sqrt{b}}[(\frac{a+\sqrt{b}}{2})^2 - (\frac{a-\sqrt{b}}{2})^2]$$

### `Solución`