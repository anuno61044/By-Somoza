# Teoría de Números 2

## Ejercicios

### `Problema 1`

> Sean $a, b_1, b_2,\ldots, b_n$ enteros con $a \ne 0$. Prueba que si $a \div b_1*b_2*\cdots*b_n$ y $a$ es primo relativo con todos los $b_i$ excepto $b_n$, entonces $a \div b_n$

### `Solución`
Procedamos por induccion:

- Caso base: para $n = 2$: Si $a \div b_1b_2$ y $mcd(a,b_1) = 1 => a \div b_2$ 
  
  Notese que si $mcd(a,b_1) = 1$ existen $x,y$ tales que $mcd(x,y) = 1$ cumpliéndose que:
  
  $$ax + b_1y = 1$$
  
  Luego, al multiplicar por $b_2$ queda que:

  $$ab_2x + b_1b_2y = b_2$$
  
  Pero como $a \div ab_2$ y $a \div b_1b_2$ por datos $\implies a \div b_2$

- Hipótesis de inducción: Supongamos que para $n = k$ se cumple que $a \div b_1b_2 \cdots b_k$ y $a$ es primo relativo con todos los $b_i$ excepto $b_k$, entonces $a \div b_k$

- Entonces, para $n = k+1$ se cumple que: como $a$ es coprimo con $b_1,b_2 \implies a$ es coprimo con $b_1b_2$. Demostrémoslo.

  - Si $mcd(a,b_1) = 1 \implies$ existen $x,y$ tal que
    
    $$ax + b_1y = 1 \implies ab_2x + b_1b_2y = b_2$$

    Como $mcd(b_2,a) = 1$ y $a \div ab_2 \implies a$ no divide a $b_1b_2$.
    
  Entonces sea $b_1b_2 = t$, luego $b_1b_2 \cdots b_{k+1} =tb_2 \cdots b_{k+1}$ y tendríamos $k$ números de los cuales $a$ es coprimo con los primeros $k-1$, por lo que $a \div b_{k+1}$ por hipótesis de inducción

### `Problema 2`

> Prueba que $mcd(n,6) = 1 \implies n^2 - 1$ es divisible por 24

### `Solución`
Notemos que $n^2 - 1 = (n+1)(n-1)$ y como $mcd(n,6) = 1 \implies n$ es impar, luego entre $n+1$ y $n-1$ uno de ellos será múltiplo de 2 y el otro múltiplo de 4 por ser dos números pares consecutivos.

Para que sea divisible $n^2-1$ por 24, como ya probamos que es divisible entre 8 (por ser divisible por 2 y 4 simultáneamente) basta demostrar que entre $n-1$ y $n+1$ hay un factor 3. Observemos que de tres números consecutivos hay uno que es múltiplo de 3, luego, $(n-1)n(n+1)$ es múltiplo de 3, pero como $mcd(n,6) = 1 \implies mcd(n,3) = 1 \implies 3 \div (n-1)(n+1)$ que es lo que queríamos probar. 

### `Problema_3`

> Sean $a,b$ enteros con $b \ne 0$. Prueba que si $a = b*q + r$ para algun $q,r$ entonces $mcd(a,b) = mcd(b,r)$

### `Solución`
Supongamos que $mcd(a,b) = d_1 \ge mcd(b,r) = d_2$, como $d_1 \div a$ y $d_1 \div b \implies d_1 \div r \implies d_1 \div mcd(b,r)$ y como $d_1 \ge d_2 \implies d_1 = d_2$. Análogamente suponiendo que $d_2 \ge d_1$

### `Problema 4`

> Sean $a_1, a_2, \ldots, a_n$ enteros no todos ceros. Prueba que $mcd(a_1,a_2,\ldots,a_n) = mcd(a_1,mcd(a_2,\ldots,a_n))$

### `Solución`
El problema podemos transformarlo en demostrar que todo divisor del miembro derecho divide al miembro iquierdo y todo divisor del miembro izquierdo divide al miembro derecho.

Supongamos que $d \div mcd(a_1,a_2,\ldots,a_n)\implies d \div a_1, d \div d_2, \ldots, d \div a_n$ entonces como $d \div a_1$ y $d$ divide al resto entonces divide a su $mcd$ y por tanto divide al $mcd(a_1,mcd(a_2,\ldots,a_n))$

Supongamos que $d \div mcd(a_1,mcd(a_2,\ldots,a_n)) \implies d \div a_1$ y $d \div mcd(a_2,\ldots,a_n) \implies d \div a_1, d \div d_2, \ldots, d \div a_n \implies d \div mcd(a_1,a_2,\ldots,a_n)$

### `Solución (Leydis Laura)`
Idea de la demostración: Agrupar los divisores comunes de $a$ y $b$ en un conjunto $A$; agrupar los divisores comunes de $b$ y $R$ en un conjunto $B$. Demostrar que $A=B$.

Sea $d \in A$, $d \div a$ y $d \div b$. Luego $d \div a*x + b*y$, donde $x,y \in \Z^+$ (resultado del ejercicio 1 de la primera clase práctica).

Por dato $a = b*q + R$, entonces $R = a - b*q$.

$R = a * (1) + b*(-q)$, luego  $R$ es combinación lineal de $a$ y $b$. Luego $d \div R$.

$d \div b$ y $d \div R \implies d \in B$ 

$\forall d \in \Z, d \in A \implies d \in B$

Luego $A \subseteq B$.

De forma análoga, podemos demostrar que $B \subseteq A$.

$A \subseteq B$ y $B \subseteq A \implies A=B$

Todo número tiene una cantidad finita de divisores. Luego $A$ y $B$ son conjuntos finitos. Como $A=B$, el mayor elemento de $A$, es el mayor elemento del conjunto $B$.

Sea $d$ el mayor elemento de $A$ y $B$. Entonces $d$ es el mayor entero positivo que es divisor común de $a$ y $b$ (puesto que $d \in A$), por tanto $d = (a,b)$. Además, $d$  es el mayor entero positivo que es divisor común de $b$ y $R$ (puesto que $d \in B$). Luego $d = (b,R)$. 
$(a,b) = (b,R)$

### `Problema_5`

> Sean $a,b$ enteros no cero los dos y $k$ entero. Prueba que $mcd(ka,kb) = k*mcd(a,b)$

### `Solución`
Para demostrar este problema demostremos el siguiente lema:

- Si $mcd(a,b) = d$, con $d = d_1d_2$ y sean $x,y$ números que cumplen que $ax + by = d$, entonces, al dividir entre $d_1$ tenemos que esos mismos $x,y$ generan la mínima combinación lineal de $\frac{a}{d}=a_1$ y $\frac{b}{d}=b_1$
  
  Supongamos que es falso, o sea, que $d_2$ no es la mínima combinación lineal de $a_1,b_1$, entonces sean $x_1,y_1$ números tal que $mcd(a_1,b_1) = d_3 \lt d_2$ y $a_1x_1 + b_1y_1 = d_3$, pero al multiplicar la ecuación por $d_1$ se cumple que $ax_1 + by_1 = d_3d_1 < d$, lo cual es falso porque $mcd(a,b) = d$

Sea $mcd(ka,kb) = d \implies$ existen $x,y$ tal que $kax + kby = d \implies k(ax + by) = d$ y como $x,y$ generan la menor combinación lineal de $ka,kb$ entonces por el lema anteriormente demostrado $ax + by = mcd(a,b)$ y por tanto $k*mcd(a,b) = mcd(ka,kb)$

### `Problema 6`

> Halla el menor entero $n$ compuesto que no es divisible por ninguno de los primeros $k$ primos

### `Solución`

### `Problema 7`

> Prueba que para todo $n$ mayor que 2 se cumple que existe $p$ primo tal que $n < p < n!$

### `Solución`

### `Problema 8`

> Sea $p_n$ el $n-esimo$ primo. Prueba que $p_n \le 2^{2^{n-1}}$

### `Solución`

### `Problema 9`
> Sean a,b enteros, mcd(a,b) = 1 y n entero positivo. Calcule:
>
> 1. $mcd(a + b, ab)$
> 2. $mcd(a + b, a - b)$
> 3. $mcd(a + b, a^2 + b^2)$
> 4. $mcd(n^2 + 1, (n+1)^2 + 1)$
