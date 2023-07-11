# Combinatoria 2

## Temas:

1. **Multiconjuntos**
2. **Permutaciones con repetición**
3. **Objetos y Categorías Iguales o Distintas**
4. **Combinaciones con repetición**
5. **Ejemplos**
6. **Binomio de Newton**
7. **Propiedades de la Combinación**
8. **Problemas y soluciones**

## Multiconjuntos

Sea $S$ un multiconjunto si cumple que es un conjunto y tiene o no elementos iguales.

## Permutaciones con Repetición

Supongamos que tenemos un multiconjunto $M = \{ a_{1_1}, \ldots, a_{1_{n_1}}, {a_{2_1}}, \ldots, a_{2_{n_2}}, \ldots, a_{k_1}, \ldots, a_{k_{n_k}}\}$ donde la cardinalidad de $M$ es $n$ y $n_1 + n_2 + \ldots + n_k = n$ y queremos hallar todas las permutaciones posibles en este.

*Por qué no es correcto aplicar la fórmula que conocemos de permutación?  $P(n) = n!$.*

Pues porque estaríamos contando las permutaciones de los elementos iguales como distintos cuando eso no es correcto. Por lo tanto necesitamos otra fórmula que aún desconocemos, pero lo que si conocemos es que las permutaciones de $n$ elementos distintos son $n!$ y sabemos hallar dados cualquier cantidad de elementos repetidos $n_i$ cuántas posibles permutaciones hay de ellos que no queremos contar.

$\therefore$ llamemos $P^n_{n_1, n_2, \ldots, n_k}$ a las permutaciones de un multiconjunto de tamaño $n$, luego, $P^n_{n_1, n_2, \ldots, n_k} * P^n_{n_1} * \ldots * P^n_{n_k} = n! \implies P^n_{n_1, n_2, \ldots, n_k} * n_1! *  n_2! * \cdots *  n_k! = n! \implies$

> $$
> P^n_{n_1, n_2, \ldots, n_k} = \frac{n!}{n_1! *  n_2! * \cdots *  n_k!}
> $$

En esta fórmula simplemente estamos dividiendo la cantidad de permutaciones totales por cada permutación de elementos repetidos para que estos se cuenten como uno solo.

### `Nota:`

> Hay una biyección entre permutar objetos en un multiconjunto y repartir $n$ onjetos en $k$ categorías donde hayan $n_1, n_2, \ldots, n_k$ objetos en cada categoría respectivamente.

## Objetos distintos en Categorías distintas

Si en un conjunto de $n$ elementos cada uno tiene una serie de $k$ categorías distintas para ser añadido, el total de formas de los elementos en las categorías  es:

> $$
> k^n
> $$

La lógica detrás de esto es usar directamente el principio de la multiplicación, el primer objeto tiene $k$ posibilidades, al igual que el segundo y así sucesivamente hasta el último  objeto, por lo tanto sería $k*k*\cdots*k,  n$-veces $\implies$ $k^n$

## Objetos iguales en Categorías distintas

La idea de repartir $n$ objetos iguales es que no hay que tener en cuenta el orden o qué objeto pusiste en una categoría que luego tienes que poner en otra, simplemente hay que trabajar con cantidades a repartir, y para esto es una buena idea usar separadores.

Si tenemos $k$ categorías significa que necesitamos $k-1$ separadores a colocar entre los $n$ objetos para separarlos en las $k$ categorías. Esto es equivalente a repartir $n+k-1$ posibles separadores de los cuales seleccionaré solo $k-1$, luego, todas las combinaciones:

> $$
> (^{n+k-1}_{k-1})
> $$

Es la cantidad de formas de colocar los separadores y por tanto de repartir $n$ objetos iguales en $k$ categorías distintas.

## Objetos iguales en categorías distintas sin que queden vacías

Aplicamos la idea anterior con los separadores pero en lugar de seleccionar $k-1$ separadores entre $n+k-1$ posibilidades, restamos $k$ para asegurarnos tener al menos un objeto en cada categoría $\therefore$ la fórmula queda de la siguiente forma $(^{n+k-1-k}_{k-1}) \implies$

> $$
> (^{n-1}_{k-1})
> $$

## Combinaciones con Repetición

En este caso queremos resolver el problema de objetos diferentes en categorías iguales. Pero podemos verlo invertido, o sea, si tomamos nuestros objetos como categorías diferentes y las categorías como objetos iguales tenemos el caso anterior.

$\therefore$ Para distribuir $n$ objetos distintos en $k$ categorías iguales basta distribuir $k$ objetos iguales en $n$ categorías distintas, lo que resulta en:

> $$
> (^{k+n-1}_{n-1})
> $$

## `Ejemplo 1`

De cuántas formas puedes comprar 10 dulces si hay tres tipos distintos?

En este caso tenemos 3 objetos distintos a repartir en 10 categorías iguales, si lo vemos al revés repartiríamos 10 objetos iguales en 3 categorías diferentes y sería de $(^{10+3-1}_{3-1})$

## `Ejemplo 2`

De cuántas formas se puede repartir $2n+1$ pelotas entre 3 niños cumpliendo que 2 niños siempre tienen juntos más pelotas que el otro?

En este problema vamos a utilizar la técnica de ir quitándo casos del total. Como hay $2n+1$ pelotas iguales a repartir entre 3 niños diferentes todas las posibilidades son: $(^{2n+1+3-1}_{3-1}) = (^{2n+3}_{2})$. Analicemos ahora de cuántas formas podemos repartir las pelotas de forma tal que no se cumpla la condición del problema, para lograrlo debemos garantizar que un niño tenga $n+1$ pelotas, y repartir las $n$ restantes entre los 3, haciendo este análisis con cada niño resulta $3*(^{n+3-1}_{3-1})$. Por tanto la cantidad de formas en que se cumple la condicion del problema es $(^{2n+3}_{2}) - 3*(^{n+3-1}_{3-1})$

## `Ejemplo 3`

Cuántos números hay de 10 dígitos divisibles por 9 cuyas cifras son 1,2,3 y el 3 aparece dos veces?

Para que un número sea múltiplo de 9 la suma de sus digitos debe ser divisible entre 9, como tengo dos cifras 3 fijas la menor suma de digitos que puedo formar es cuando los 8 dígitos restantes sean 1 y esto resulta en 14, la máxima suma de dígitos que puedo formar es cuando las 8 cifras restantes sean 2 y da como resultado 22 $\implies$ la suma de los dígitos debe ser 18.

Sea $a$ la cantidad de unos del número y $b$ la cantidad de dos, entonces resolviendo el sistema:

$$
a+b = 8
$$

$$
a+2b = 12
$$

Llegamos a que $a=b=4$, y por último basta permutar dos 3, cuatro 1 y cuatro 2 para obtener la respuesta:
$P^{10}_{2,3,4} = \frac{10!}{2!*4!*4!}$ .

## Binomio de Newton

> $$
> (a+b)^n = \sum_{k = 0}^{n}(^n_k)a^{n-k}b^k
> $$

Por qué esta fórmula? O sea, por qué al multiplicar $(a+b)*(a+b)* \cdots *(a+b)$ resulta en la sumatoria anterior?

Notemos que en cada sumando debe haber $n$ factores entre $a$ y $b$, pudiendo no estar ambos simnultaneamente como es el caso de $a^n$ y $b^n$, entonces, es fácil ver que hay $n$ sumandos porque $(^n_2) = n$ es decir, conjuntos de $n$ elementos en  escogiendo entre 2 posibilidades.

Tomemos para analizar el sumando $a^{n-i}b^i$ para saber cuántas cadenas puedo formar con esta cantidad de $a$ y $b$ y así saber que coeficiente asignarle a este término. Veamos que el problema se reduce a de cuántas formas podemos escoger $i$ cantidad de $b$ entre los $n$ factores de $(a+b)^n$, ya que el resto del término será llenado con $a$ de los demás factores, y la cantidad de formas de seleccionar $i$ entre $n$ posibilidades no es más que $(^n_i)$, por tanto el término $i$-$ésimo$ de la sumatoria queda de la forma $(^n_i)a^{n-i}b^i$.

## Propiedades de la Combinación

> $$
> k(^n_k) = n(^{n-1}_{k-1})
> $$

Notemos que si dadas $n$ personas seleccionamos subconjuntos de $k$ personas serían $(^n_k)$ formas y de cada una vemos de cuántas formas podemos seleccionar un líder entre las $k$ personas que forman cada subconjunto, lo cual nos da el miembro izquierdo. En el miembro derecho, para cada persona de las $n$ que hay, vamos a calcular cuántas veces esa persona es líder de un grupo de $k$, eso implica que hay que calcular teniendo una persona fija cuántos grupos de $k-1$ se pueden formar con las restantes $n-1$ personas $\implies$ $(^{n-1}_{k-1})$ $\therefore$ es $n(^{n-1}_{k-1})$

> $$
> n(^{n-1}_{k-1}) = (^n_{k-1})(n-k+1)
> $$

Recordemos que el miembro izquierdo nos da la cantidad de formas de seleccionar un líder por cada subconjunto de $k$. En el miembro derecho la idea es generar todos los posibles subconjuntos de $k-1$ y por cada uno seleccionamos una persona distinta de esas como líder, y ser;ia el elemento $k$-$esimo$ que eligiríamos entre las restantes $n-k+1$ personas $\implies (^n_{k-1})(n-k+1)$

> $$
> (^k_k) + (^{k+1}_k) + \cdots + (^n_k) = (^{n+1}_{k+1})
> $$

Vamos a demostrarlo por inducción:

- Caso base $n=k$ se cumple que $(^k_k)=(^{k+1}_{k+1})$
- Hipótesis de inducción $ (^k_k) + (^{k+1}_k) + \cdots + (^n_k) = (^{n+1}_{k+1})$ se cumple hasta $n$
- Demostremos que se cumple para $n+1$, notemos que la suma de los $n$ primeros términos de la sumatoria $(^k_k) + (^{k+1}_k) + \cdots + (^n_k) + (^{n+1}_k)$ por hipótesis de inducción es igual a $(^{n+1}_{k+1})$ por lo que bastaría probar que $(^{n+1}_{k+1}) + (^{n+1}_k) = (^{n+2}_{k+1})$ y esto podemos demostrarlo fácilmente con el siguiente problema: De cuántas formas puedo hacer grupos de $K+1$ teniendo $n+2$ elementos totales
- - El miembro derecho de la igualdad es exactamente la solución al problema que tenemos planteado
- - Otra forma de bver a solución es fijando un elemento, y haciendo grupos donde este esté y luego grupos donde no esté, la cantidad total de formas de hacer esto resulta el miembro izquierdo.

> $$
> (^n_k) = (^n_{n-k})
> $$

Nótese que si tenemos $n$ elementos y una cadena de tamaño $n$ en las primeras $k$ posiciones puedo colocar $n$ elementos de $(^n_k)$ y por cada una tengo una distribución única en las restantes $n-k$ posiciones. Si analizamos ahora en una cadena de $n$ posiciones la cantidad de formas de llenar $n-k$ posiciones resulta en $(^n_{n-k})$ y para cada una de estas hay una única forma de distribuir el resto en $k$ posiciones. Como se puede establecer una biyección en la cantidad de formas de repartir en $n-k$ y en $k$ entonces $(^n_k) = (^n_{n-k})$

> $$
> (^n_k) = (^{n-1}_k)+(^{n-1}_{k-1})
> $$

Recordemos que $(^n_k)$ es la cantidad de formas de hacer subconjuntos de tamaño $k$ con $n$ elementos. Veámoslo ahora de esta forma, sea $a$ uno de los $n$ elementos, la cantidad de formas de hacer subconjuntos de tamaño $k$ es equivalente a la cantidad de formas de hacer los subconjuntos con el elemento $a$ más la cantidad de formas en las que no está $a$. En la primera distribuimos $n-1$ elementos en $k-1$ posiciones $\implies (^{n-1}_{k-1})$ y en la segunda distribuimos $n-1$ elementos en $k$ posiciones $\implies (^{n-1}_{k})$

## `Ejemplo 4`

A una fiesta a la que asisten $n$ personas hay 3 tipos de tragos y uno de ellos tiene alcohol, para que todas las personas selecciones uno de ellos. Teniendo en cuenta que de las $n$ personas hay exactamente una que debe conducir de regreso a su casa (o sea que no puede escoger el trago con alcohol) prueba que las posibilidades de que ocurran las situaciones anteriores son:

$$
2*n*3^{n-1} = \sum^n_{k=1}2^k*(^n_k)*k
$$

El miembro izquiero nos dice la cantidad de posibilidades pero enfocadas al chofer, o sea, tengo $n$ formas de seleccionar el chofer, por cada una de ellas puede seleccionar 2 tragos (sin alcohol) y el resto de las $n-1$ personas pueden seleccionar cualquiera de los 3 tragos $\implies 2*n*3^{n-1}$.

En el caso del miembro derecho nos enfocamos en las personas que van a seleccionar cualquiera de los 2 tragos sin alcohol. Hay $(^n_k)$ formas para esas $k$ personas (con $k$ desde 1 hasta $n$), por cada una podemos seleccionar los tragos sin alcohol de $2^k$ formas y seleccionar a la vez $k$ posibles choferes, el resto de las $n$ personas toman alcohol, ya que analizamos cada posibilidad de extraer las $k$ que no toman alcohol $\implies$ la fórmula quedaría $\sum^n_{k=1}2^k*(^n_k)*k$

## Problemas y Soluciones

### `Problema 1`

> Calcule el número de soluciones $x_1 + x_2 + x_3 + x_4 = 50$ donde los $x_i$ son impares.

### `Solución 1 (Somoza)`

Si analizamos llegamos a la concluisón que el problema se reduce a que: a partir de un conjunto de $50$ elementos seleccionar 4 subconjuntos con cantidad impar, lo cual podemos resolver agregando 3 separadores y la cantidad de formas de colocarlos en posiciones pares $(\lfloor \frac{50}{2} \rfloor)$ nos dará la solución que buscamos, lo cual sería $(^{26}_3)$.

### `Solución 2 (Somoza)`

Notemos que si los $x_i$ son impares podemos representarlos cada uno como $2y_i - 1$ donde $y_i \ge 0$, por tanto $x_1 + x_2 + x_3 + x_4 = 2y_1 - 1 + 2y_2 - 1 + 2y_3 - 1 + 2y_4 - 1 = 50 \implies 2y_1 + 2y_2 + 2y_3 + 2y_4 = 54 \implies y_1 + y_2 + y_3 + y_4 = 27$, pero como los $y_i$ no pueden estar vacíos debemos repartir 4 elementos, uno en cada conjunto, y nos quedaría 23 elementos iguales a repartir en 4 categorías distintas $\implies (^{23+4-1}_{4-1}) \implies (^{26}_{3})$.

### `Problema 2`

> Encuentre una expresión para computar $(x_1 + x_2 + \cdots + x_k)^n$

### `Solución`
Sea la expresión:
$$(x_1 + x_2 + \cdots + x_k)^n = \sum_{n_1+n_2+\cdots +n_k=n} \frac{n!}{n_1!n_2!\cdots n_k!}x_1^{n_1}x_2^{n_2}\cdots x_k^{n_k}$$

Cada sumando en el miembro derecho tiene en total $n$ factores porque es el resultado de la multiplicación $n$ veces de $(x_1 + x_2 + \cdots + x_k)$, por lo cual, los exponentes de los factores $x_i$ de dichos sumandos deben sumar $n$. Luego, basta con calcular dado una distribución de esos exponentes de cuántas formas la podemos generar, lo cual resulta una permutación con repetición.

### `Problema 3`

> Demuestre:
>
> 1. $\sum^{n}_{k=0}(-1)^k(^n_k) = 0$
> 2. $\sum^{n}_{k=0}(^n_k)^2 = (^{2n}_n)$
> 3. $\sum^{n}_{k=0}k(^n_k) = n2^{n-1}$

### `1.Solución`

Primero vamos a contar de cuántas formas podemos contar todos los posibles subconjuntos de cualquier cardinalidad de un conjunto con $n$ elementos $A$ en los que no aparezca el elemento $a_0$, y sean estos subconjuntos $A_1,A_2,\ldots,A_k$. Observemos que, si los contamos a ellos y los volvemos a contar pero esta vez añadiéndole a cada uno el elemento $a_0$ obtendríamos todos los posibles subconjuntos de $A$, y veámoslos de esta forma:

| Subconjuntos | Subconjuntos con$a_0$ |
| :----------- | :---------------------- |
| $A_1$      | $A_1 \cup \{a_0\}$    |
| $A_2$      | $A_2 \cup \{a_0\}$    |
| $\cdots$   | $\cdots$              |
| $A_k$      | $A_k \cup \{a_0\}$    |

En esta distribución todos los subconjuntos son distintos y hay por cada fila un subconjunto par y otro impar (porque solos se diferencian en el elemento $a_0$), por tanto, hay la misma cantidad de subconjuntos pares que de impares dado un conjunto $A$, por lo que $\sum{_{1 \le p \le n : p-par}}(^n_p)=\sum{_{1 \le i \le n : i-impar}}(^n_i)$ por lo que al restar los pares menos los impares que es la fórmula que queremos probar resulta cero.

### `2.Solución (Marlon)`

El miembro derecho lo podemos ver como la cantidad de formas de seleccionar $n$ elementos de un conjunto con $2n \implies (^{2n}_n)$. Esto es equivalente a particionar el conjunto en 2 subconjuntos de $n$ elementos cada uno y por cada forma $(^n_k)$ de seleccionar $k$ elementos en el primero tomar $n-k$ del segundo (^n_{n-k}) y esto último es equivalente a $(^n_k) \implies (^n_k)^2$, lo cual nos daría todas las formas de seleccionar subconjuntos de $n$ elementos $\implies \sum^{n}_{k=0}(^n_k)^2$

### `3.Solución`

Notemos que el miembro izquierdo podemos verlo como de cuántas formas podemos seleccionar por cada posible subconjunto de un conjunto de $n$ personas un líder para cada uno, cumpliéndo que este se encuentre dentro del conjunto, entonces para cada subconjunto de tamaño $k$ tendremos $k$ posibles líderes de sus miembros, y esto es $\sum^{n}_{k=0}k(^n_k)$. El miembro derecho es eso mismo pero enfocado de esta forma: para cada miembro del conjunto hay $n$ personas que pueden ser líder, y a cada una de ellas le podemos asignar un grupo a liderar con las restantes $n-1$ personas de $2^{n-1}$ posibilidades.

### `Problema 4`

> Calcule el número de subconjuntos $X$ de tamaño $k$ del conjunto $\{1,2,\ldots,n\}$ tal que $\forall a,b \isin X$ se cumple que $|a-b| \ge 3$.

### `Solución (David)`

Si analizamos el problema de hacer subconjuntos de tamaño $k$ a partir de un conjunto de $n$ donde no haya elementos consecutivos resulta que: si lo vemos como cadenas binarias donde 1 en la posición $i$ es que seleccionamos el elemento $i$-ésimo y 0 si no lo hacemos, como seleccionamos $k$ elementos debemos agregar siempre entre ellos $k-1$ ceros, por lo que, la cantidad de posibilidades para colocar los unos se $(^{n-(k-1)})$.

En el problema en cuestión la diferencia es que  entre cada uno no colocamos un cero, sino 2, por lo que basta restar $n-2(k-1)$ y el resultado hacer combinaciones en $k \implies (^{n-2(k-1)}_k)$

### `Solución`

Tenemos una cadena binaria de $n$ bits donde seleccionaremos $k$ unos que serán las posiciones de los elementos que escogeremos, luego, de los restantes $n-k$ elementos que serán todos ceros restamos $2(k-1)$ ceros que colocaremos después de cada uno añadido garantizando que la diferencia modular entre cada elemento sea al menos 3, lo que nos queda es repartir el resto de ceros entre las $k+1$ posiciones disponibles (entre los unos, antes de ellos y después de ellos), lo cual hacemos con el uso de $k$ separadores que tendríamos que adicionarle a $n-k-2(k-1)$, por lo que la fórmula final quedaría $(^{n-2k+2}_k)$

### `Problema 5`
> Calcule el número de arreglos de tamaño $n$ ordenados de menor a mayor donde cada elemento es un número de 1 a n.

### `Solución`
Notemos que si denominamos objetos a los números y categorías a las posiciones estaremos contando cuántas formas hay para repartir $n$ objetos distintos en $n$ categorías iguales con repetición, lo cual no sabemos hacer, pero si tomamos como categorías los números y como objetos las posiciones necesitaríamos contar las formas de repartir $n$ objetos iguales en $n$ categorías distintas, y eso si lo sabemos hacer.
$$(^{n+n-1}_{n+1})=(^{2n-1}_{n+1})$$ 

### `Problema 6`
> Hay 12 bombillos alineados en una fila, y empezando a enumerar los bombillos desde uno, los bombillos 3,7 y 11 están encendidos. En cada paso se enciende un bombillo pero solo si está junto a uno ya encendido. Calcule de cuántas formas distintas se logran encender todos.

### `Solución 6`

Tengamos esta distribución inicial de bombillos donde 0 es que el bombillo en esa posición está apagado y 1 que está encendido 0 0 1 0 0 0 1 0 0 0 1 0.

Para cada grupo de $k$ ceros consecutivos hay una forma valida de encenderlo si el grupo tiene un solo bombillo encendido a algún lado, de lo contrario hay $2^{k-1}$ formas válidas porque en cada momento podemos encender apoyándonos en el bombillo a la izquierda o en el bombillo a la derecha, hasta que nos quede un solo bombillo el cual solo tiene una posibilidad $\implies 2^{k-1}$, como tengo grupos de 2,3,3,1 bombillos apagados, por cada uno tengo respectivamente $1, 2^2,2^2,1$ formas de encenderlos, pero el orden en que puedo encender cualquier bombillo válido en un grupo viene dado por las permutaciones con repetición de 12-3=9 en 2,3,3,1
$\implies \frac{9!}{2!*3!*3!*1!}$ y como para cada posible orden en los grupos que enciendo tengo una forma particular de encender cada uno $\implies 1*2^2*2^2*1*\frac{9!}{2!*3!*3!*1!}$

### `Problema 7`
> De cuántas formas se particiona un conjunto de $n$ elementos en $j_1$ subconjuntos de tamaño 1, $j_2$ de tamaño 2 hasta $j_k$ subconjuntos de tamaño $k$.

### `Solución`
Supongamos primeramente que $n=1+2+\cdots+k$ y calculemos la cantidad de $k-$particiones cuyos subconjuntos tienen tamaño $1,2,\ldots,k$ respectivamente. Notemos que si formamos todas las particiones y de ellas seleccionamos los subconjuntos de tamaño $1,2,\ldots,k$ empezando desde el primero hasta el último estaríamos contando en cada partición el subconjunto de tamaño $i$ de $i!$ formas que son equivalentes, por lo que, por cada subconjunto de tamaño $i$ debemos dividir el total de permutaciones por $i!$

Acercándonos más ea problema que queremos resolver, ahora tenemos $j_1$ subconjuntos de tamaño 1, $j_2$ de tamaño 2 hasta $j_k$ subconjuntos de tamaño $k$, y utilizando el razonamiento anterior la cantidad de formas de hacer esto es:
$$\frac{n!}{1!^{j_1}*2!^{j_2}*\cdots*k!^{j_k}}$$

Sin embargo, en este caso tenemos $j_i$ subconjuntos de tamaño $i$, de los cuales, estamos contando todas sus posibles permutaciones, por lo que, para cada $i$, es necesario dividir la expresión anterior entre $j_i!$. Por tanto, la fórmula final sería la siguiente:

## $$\frac{n!}{(1!^{j_1}*2!^{j_2}*\cdots*k!^{j_k})(j_1!*j_2!*\cdots*j_k!)}$$
