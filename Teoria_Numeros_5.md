# Teoría de Números 5

## Temas

## Ejercicios

### `Problema 1`
> Demuestre o refute
> - $37621+2^{30} + 471 + 59603*25$ es divisible por $12$
> - $375121*4^{105} - 35^{91}$ es primo relativo con 6 y el número $9^{1684}-7^{52688}$ es divisible por 10
> - $2^{70}+3^{70}$ es divisible por 13
> - $3^{47}$ deja resto 4 cuando se divide por 23 

### `Solución`

### `Problema 2`
> Prueba que es finita la cantidad de números $k$ tal que $\sum^{\infty}_{k=1}$ $k!$ es un cuadrado perfecto.

### `Solución`
Sea $S(t) = \sum^t_{k=1}$. Nótese que para los siguientes casos:
- $S(1) = 1$ cumple
- $S(2) = 3$ no cumple
- $S(3) = 9$ cumple
- $S(4) = 33$ no cumple
- $S(5) = 153$ no cumple
- $S(6) = 873$ tampoco

Para $t \ge 7$ tenemos que los terminos $i!$ en la sumatoria a partir de 7! serán divisibles entre 7, entonces la congruencia de $S(t)$ módulo 7 no va a variar. Como los cuadrados perfectos solo dejan resto 1, 4, 2 , 0 módulo 7 y $S(6)$ deja resto 5, se cumple que para $t \gt 6$ no existe t tal que $S(t)$ sea un cuadrado perfecto.

### `Problema 3`
> Prueba que las siguientes ecuaciones no tienen solución:
> - $3x^2 + 5 + 9xy = y^2$
> - $x^4 - 5x^3 + 30x^2 = 18$
> - $x^2 + y^2 - 8z = 6$

### `Solución`
1. $$3x^2 + 5 + 9xy = y^2$$
La ecuación puede transformarse en $3x(x + 3y) = y^2 - 5$. Nótese que $3x(x + 3y) \equiv 0$ $mod(3)$, por tanto $y^2 - 5 \equiv 0$ $mod(3) \implies y^2 \equiv 5$ $mod(3) \implies y^2 \equiv -1$ $mod(3)$ lo cual es imposible porque los cuadrados son congruentes con 0 o 1 módulo 3.

2. $$x^4 - 5x^3 + 30x^2 = 18$$
La ecuacion puede transformarse en $x^2(x^2 - 5x + 30) = 18$. Nótese que $18 \equiv 3$ $mod(5)$ y como todo cuadrado es congruente con 0, 1 0 -1 módulo 5 entonces $x^2(x^2 - 5x + 30) \equiv x^2(x^2)$ $mod(5)$ y $x^4 \equiv 0, 1$ $mod(5)$ lo cual genera una contradicción.

3. $$x^2 + y^2 - 8z = 6$$
Esta ecuacion no es necesario ni transformarla, $6 \equiv 6$ $mod(8)$, $8z \equiv 0$ $mod(8)$ y como los cuadrados son congruentes con 0,1,4 módulo 8 entonces $x^2 + y^2 \equiv 0,2$ $mod(8)$ contradicción.

### `Problema 4`
> Demuestre que dados 3 números cualesquiera enteros siempre es posible seleccionar dos tal que $a^3 * b - a * b^3$ es divisible por 10.

### `Solución`
Nótese que $a^3 * b - a * b^3 = ab(a^2 - b^2)$, y que cualquier número $x^2 \equiv 0,1,-1$ $mod(5)$. Hagamos el siguiente análisis:
- Para que sea divisible entre 10 debe ser divisible por 2 y 5 simultáneamente, y la expresión $ab(a^2 - b^2)$ es evidente que para cualquier $a,b$ es par (supongamos que al menos uno de los dos en par $\implies$ el producto es par, en caso contrario, ambos son impares $\implies$ su diferencia es par).
- Si tomamos como uno de los tres números a seleccionar $x \equiv 0$ $mod(5)$ es trivial que el resultado será divisile por 5, luego, seleccionando los otros 2 restos distintos de cero para los cuadrados de los números tenemos las posibilidades 1,-1 para tres números, de los cuales por Principio de las Casillas dos tendrán el mismo resto y su diferencia será cero módulo 5, lo cual demuestra la orden del ejercicio.

### `Problema 5`
> Un número es de Fermat si es $2^{2^n} + 1$ para todo $n \ge 0$. 
> - Prueba que todos los números de Fermat son primos relativos dos a dos. 
> - Prueba que hay infinitos primos con esta demostración. *

### `Solución`
Tenemos los números $2^{2^r} + 1$ y $2^{2^s} + 1$. Supongamos que existe un número p que divide a ambos, entonces $2^{2^r} \equiv -1$ $mod(p)$, sin pérdida de generalidad $s \gt r$, luego al elevar $2^{2^r}$ al cuadrado $s-r$ veces resulta que $2^{2^s} \equiv 1$ $mod(p)$, lo cual es una contradicción porque $2^{2^s} \equiv -1$ $mod(p)$, en cuyo caso $p$ debería ser 2, lo cual es absurdo.

### `Problema 6`
> Halla $a,b,c$ tal que $2^a + 2^b = c!$

### `Solución`
Nótese que $2^a + 2^b = 2^b(2^{b_1} + 1)$  suponiendo que $a = b + b_1$ con $b_1 > 0$ , o sea $a \gt b$, luego para $c \ge 7$ tenemos que $c! \equiv 0$ $mod(7)$ y cualquier potencia de 2 es congruente con 1,2,4 módulo 7, luego no existe ninguna distribucion de esos restos que cumpla que  $2^b(2^b_1 + 1) \equiv 0$ $mod(7)$. Para $c \lt 7$ probando llegamos a que son soluciones $(0,0,2)$, $(1,2,3)$ y $(4,3,4)$
