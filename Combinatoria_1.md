# Combinatoria 1

## Temas:
1. **Principio de la Adicion**
2. **Principio de la Multiplicacion**
3. **Biyecciones**
4. **k-Permutacion (sin repeticion)**
5. **k-Combinacion (sin repeticion)**
6. **Ejemplos**
7. **Problemas y soluciones**


## Principio de la Adicion
Si un suceso A puede ocurrir de n maneras y un suceso B puede ocurrir de m maneras y, A y B no pueden ocurrir simultáneamente, entonces el suceso A o B sucede de n + m maneras diferentes.

## Principio de la Multiplicacion
Si un primer objeto puede escogerse entre n posibles, y después un segundo objeto puede escogerse entre m posibles, entonces simultáneamente ambos objetos pueden escogerse de nm maneras distintas.

## Biyeciones
Sea $N_n = { 1, 2, ..., n }$ decimos que un conjunto A tiene n elementos o que |A| = n si existe f : $N_n$ $\rightarrow$ A biyectiva.

Sean A y B conjuntos finitos, si A ∩ B = ∅ entonces |A ∪ B| = |A| + |B|.

## k-Permutaciones
Una permutación de n objetos es una ordenación de estos en fila. Se denota por $P(n)$ o por $P_n$. Además $P_n$ = n!.

Una k−permutación (conocido también como variaciones) de un conjunto S, es una secuencia de k elementos distintos de S. Se denota por $P(n, k)$ o por $V^n_k$. Además $V^n_k = n!*(n−k)!$.

## k-Combinaciones
Si se tienen n objetos, una combinación de k en n, es una combinación de k objetos tomados de los n. Se denota por $C(n, k)$, por $C^n_k$ o por $(^n_k)$.  Además $(^n_k)$ = $\frac{n!}{k!*(n-k)!}$  

***  

## Ejemplos

### `Ejemplo 1`
> Cuantas cadenas hay de longitud 7 sin caracteres repetidos y $a,d$ no aparecen juntas. Suponga que el alfabeto tiene 26 caracteres.

### `Solucion`
Resolvamos el problema construyendo la solucion, analicemos estos casos:

1. No aparecen ni $a$ ni $d$ en la cadena:

Entonces basta permutar las restantes 24 letras en los 7 espacios disponibles. Por tanto $P(24,7) = \frac{24!}{17!}$

2. Aparece una de las letras pero no la otra:

En ese caso tenemos 7 posibles espacios para colocar una letra y 6 espacios para permutar las 24 restantes, luego haciendo este analisis para $a$ y para $d$ tendriamos $7*P(24,6) + 7*P(24,6) = 2*7*P(24,6)$

3. Aparece $a$ en la esquina

Ahora tenemos 2 posibilidades de colocar $a$ porque tenemos 2 esquinas, por lo tanto $d$ la podemos colocar en los 5 espacios que no estan consecutivos a las esquinas. Por tanto seria $2*5*P(24,5)$

4. Aparece $a$ en el centro

Como $a$ esta en el centro significa que hay 2 posiciones consecutivas a $a$ donde $d$ no puede estar, por tanto hay 5 posibilidades de poner $a$ en el centro, por cada una de ellas hay 4 formas de poner la $d$ y $P(24,5)$ ormas de permutar el resto de las letras, luego seria $5*4*P(24,5)$

Por tanto, la cantidad de formas totales en que se pueden formas cadenas de 7 caracteres diferentes donde la $a$ y la $d$ no aparezcan juntas es:

$S = \frac{24!}{7!*17!} + 2*7*P(24,6) + 2*5*P(24,5) + 5*4*P(24,5)$

### `Ejemplo 2`
> Es conocido que la serie $\sum_{k=1}^n \frac{1}{k}$ diverge. Qué ocurrirá si extraemos todos los 2 de todos los términos que lo contengan en la serie?

### `Solución`
Nótese que aplicando técnicas básicas de conteo hay $8*9^{n-1}$ números que no contienen a un digito específico (en nuestro caso al 2). Entonces ocurre que:

Para 1 digito sea $S_1 = \frac{1}{1} + \frac{1}{3} + \cdots + \frac{1}{9}$ hay $8$ números que no contienen al 2 y todos son menores que $\frac{1}{1}$, lo que implica que $S \leq 8*9$

Para 2 digitos sea $S_2 = \frac{1}{10} + \frac{1}{11} + \cdots + \frac{1}{99}$ hay $8*9$ números que no contienen al 2 y todos son menores que $\frac{1}{10}$, lo que implica que $S \leq 8*\frac{9}{10}$

Y así sucesivamente es evidente que se cumple para n digitos, luego la serie original $\sum_{k=1}^n \frac{1}{n}$ estará acotada superiormente por la serie $\sum_{k=0}^n 8*\frac{9}{10^k}$ y como esta última es evidente que converge la original también con la condición planteada en el ejercicio.

***

## Ejercicios CP

### `Problema 1`
> Determine el número de subconjuntos de tamaño $k$ que se pueden formar a partir del conjunto $A = \{1,2,\ldots,n\}$ donde no existan dos elementos consecutivos del conjunto original.

### `Solucion (Somoza)`
Construyamos el conjunto que podemos formar a partir de una máscara de bits donde 1 en el $i-esimo$ bit es si cogemos el $i-esimo$ elemento del conjunto, como tenemos que colocar $k$ elementos tendremos $n-k$ ceros y entre cada uno, al comienzo y al final de la cadena podemos colocar 1, serian entonces $n-k+1$ posibilidades de poner $k$ unos. Por tanto la solución sería $(^{n-k+1}_k)$

### `Problema 2`
> Calcule el número de enteros de 5 digitos divisibles por 3 que contienen al 9.

### `Solución (Somoza)`
Con 5 digitos existen $9*10^4$ números en total con todas sus cifras. De ellos $8*9^4$ no contienen al 9, o sea, quitamos una cifra en cada posición. Si mantenemos las primeras cuatro posiciones $\overline{abcd}$ vemos que en la última hay que analizar estos 3 casos en dependencia de la divisibilidad de la suma de esos digitos módulo 3:
1. $\overline{abcd} \equiv 0 \mod(3) \implies$ el dígito $e$ debe cumplir que $e \equiv0 \mod(3)$ para mantener la divisibilidad $\implies$ $e = {0,3,6}$ tres posibilidades.
2. $\overline{abcd} \equiv 1 \mod(3) \implies$ el dígito $e$ debe cumplir que $e \equiv 2 \mod(3)$ para mantener la divisibilidad $\implies$ $e = {2,5,8}$ tres posibilidades.
3. $\overline{abcd} \equiv 2 \mod(3) \implies$ el dígito $e$ debe cumplir que $e \equiv 1 \mod(3)$ para mantener la divisibilidad $\implies$ $e = {1,4,7}$ tres posibilidades.

Entonces tenemos $8*9^3*3$ números que son divisibles entre 3 y no contienen al 9, basta hallar la cantidad de números totales que son divisibles entre 3, que son $3*10^4$ y restarle esta cantidad y tendremos la respuesta a nuestro problema.

### `Problema 3`
> Sean $n,k$ $\in \Z_+$ y $A$ un conjunto de tamaño $n$. Calcule el número de $k-$uplas $<A_1, A_2, \ldots, A_k>$ de subconjuntos de $A$ que cumplen que:
> 1. $A_1 \subseteq A_2 \subseteq A_3 \subseteq \ldots \subseteq A_k$
> 2. $A_1 \cap A_2 \cap A_3 \cap \ldots \cap A_k = \emptyset$

### `Solución 1`
Nótese que basta asignarle a cada elemento del conjunto $A$ un subconjunto entre 1 y $k$ para que este esté en los conjuntos superiores. Entonces, el problema se reduce a contar de cuántas formas podemos asignarle un subconjunto entre los $k$ posibles a cada uno de los $n$ elementos, existiendo la posibilidad $(k+1)$-esima de no asignarle ningún conjunto a un elemento, entonces hay en total $(k+1)^n$ formas.

### `Solución 2`
Para que se cumpla que la intersección sea nula debe cumplirse que cada elemento debe estar a lo sumo en $k-1$ subconjuntos, y la cantidad de formas de hacer esto con cada elemento entre los $n$ posibles es $2^k - 1$, y restamos uno porque quitamos el caso en que este elemento se encuentre en todos los k subconjuntos.

$\therefore$ el número total de formas, usando el principio de la multiplicación con los $n$ elementos es $(2^k - 1)^n$

### `Problema 4`
> Sea $A$ un conjunto de tamaño $n$. Calcule:
> 1. Cuántas relaciones binarias se definen en $A$?
> 2. Cuántas relaciones reflexivas se definen en $A$?
> 3. Cuántas relaciones simétricas se definen en $A$?
> 4. Cuántas relaciones asimétricas se definen en $A$?
> 5. Cuántas relaciones antisimétricas se definen en $A$?

### `Solución`
1. Como el conjunto $A$ tiene $n$ elementos al contar las relaciones binarias contamos cada elemento con cualquiera de los $n$ posibles $\implies 2^{n^2}$
2. Las relaciones reflexivas deben tener necesariamente cada elemento relacionado con el mismo $\implies n$ elementos, porque no pueden existir en el conjunto elementos que no estén relacionados con él mismo en la relación reflexiva. Teniendo esto basta generar el resto de elementos en la relación que serían $n*(n-1)$ pares, los cuales generan $2^{n*(n-1)}$
3. Las relaciones simétricas si contienen al par $\langle a,b \rangle$ también contienen al par $\langle b,a \rangle$, por lo que basta contar cuántos conjuntos puedo formar con $\frac{n^2}{2}$ que serían en total $2^\frac{n^2}{2}$
4. Las relaciones asimétricas son aquellas que si contienen al elemento $\langle a,b \rangle$ no contienen al $\langle b,a \rangle$ $\implies$ basta tomar todos los pares $\langle a,b \rangle$ con $a < b$ que son en total $\frac{n*(n-1)}{2}$ y cada uno de estos puede estar en el subconjunto, no estar o estar su simétrico $\therefore$ existen en total $3^{\frac{n*(n-1)}{2}}$.
5. En las relaciones antisimétricas, si está el par $\langle a,b \rangle$ y el par $\langle b,a \rangle \implies a = b$. Nótese que por cada relación asimétrica, si le agregamos o no un subconjunto de pares reflexivos se convierte en antisimétrica $\therefore$ en total existen $3^{\frac{n*(n-1)}{2}} * 2^n$. 

### `Problema 5`
> Sea $E$ un conjunto de cardinalidad $n$. Calcule el número de pares de subconjuntos no ordenadosni nulos $A,B$ tales que tengan intersección nula.

### `Solución`
Nótese que la cantidad de formas totales de repartir n elementos en los 2 subconjuntos pudiendo cada elemento no estar en ninguno y garantizando que un elemento pertenezca solo a un subconjunto es $3^n$. Luego, la cantidad de formas de colocar los elementos en $A$ y no en $B$ es $2^n$ y análogamente colocar en $B$ y no en $A \implies$ la cantidad de formas de dejar al menos un subconjunto vacío es $2*2^n$ por el *Principio de la Suma* $\therefore$ la cantidad de pares de subconjuntos no ordenadosni nulos $A,B$ tales que tengan intersección nula es $3^n - 2^{n+1}$.

### `Problema 6`
> Una permutación de $n$ números es más o menos cresciente si solo existe un único par de elementos $a_i, a_j$ de la permutación tal que $i<j$ y $a_i > a_j$. Cuántas permutaciones casi crescientes hay en el conjunto 

### `Solución`
La cantidad de permutaciones no crescientes es equivalente a la cantidad de inversiones de 2 elementos que puedo hacer en el conjunto de $n$ elementos ordenados, la cual es $(^n_2)$.

### `Problema 7`
> Una permutación de $n$ números es casi cresciente si solo existe un único $k$ con $k \lt n-1$ tal que $a_k > a_{k+1}$. Cuántas permutaciones casi crescientes hay en el conjunto?

### `Solución`
