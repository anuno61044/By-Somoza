# Combinatoria 4

### `Definición de Recurrencia lineal`
Sea $f: \R^k \to \R$ y sean $c_0, c_1,\dots, c_{k-1}\in \R$ dados, entonces $\exist !$ $a_0,a_1,\dots,a_{k-1}$ tal que $a_n = f(a_{n-1},a_{n-2},\dots,a_{n-k})$ con $n \ge k$ y $a_0 = c_0, a_1 = c_1, \dots, a_{k-1}=c_{k-1}$

Notemos que dada cualquier secuencia de orden $k$, ejemplo: $a_n = 7a_{n-1}-10a_{n-2}$ existe una única secuencia que empieza definida por $k$ valores, ejemplo $(7,15)$.

En este caso particular $2^n$ y $5^n$ son funciones que cumplen la recurrencia pero ninguna de ellas empieza por 7 y 15.

## Ejemplos

### `Ejemplo 1`
> Cuántas regiones forman $n$ líneas en el plano que no sean paralelas y ningún trío se corte en un punto?

Si tengo $a_{n-1}$ regiones con $n-1$ líneas, al añadir otra línea que viene del infinito, como esta no es paralela con ninguna y no pasa por la intersección de dos líneas ya existentes en el plano, siempre forma una nueva región con cada línea que intersecta. La fórmula de recurrencia quedaría de la siguiente forma $a_n = a_{n-1}+n$

### `Ejemplo 2 (Problema de Josefo)`
> De cuántas formas puedo subir una escalera de 20 escalones con 1 o 2 pasos?

La cantidad de formas de subir $n$ escalones podemos verla definida como la cantidad de formas de llegar al escalón $n-1$, del cual solo habría una forma de llegar al último escalón (dando un paso), más la cantidad de formas de llegar al escalón $n-2$, del cual solo habría que dar dos pasos para llegar al último, por tanto la recurrencia resulta en $a_n = a_{n-1}+a_{n-2}$ siendo $a_1 = 1$ y $a_2 = 2$

> Y si el orden no importara?

Si el orden no importa, la cantidad de formas de dar dos pasos es $\frac{n}{2}+1$ porque es una posibilidad no dar pasos de dos.

### `Ejemplo 3`
> Una compañía $A$ tiene tiendas en La Habana y Santiago de Cuba, los carros se rentan para ciajes locales e interprovinciales. Después de cada mes la mitad de los carros que comienzan en Habana terminan en Santiago y $\frac{1}{3}$ de los que empiezan en Santiago terminan en Habana. Si empiezan con 1000 carros en cada tienda, con cuántos terminan en La Habana después de $n$ meses.

La recurrencia queda de la siguiente forma con $s_1 = h_1 = 1000$:
1. $h_n = \frac{1}{2}h_{n-1} + \frac{1}{3}s_{n-1}$
2. $s_n = \frac{2}{3}s_{n-1} + \frac{1}{2}h_{n-1}$

Despejemos $s_{n-1}$ de la ecuación 1 y sustituyamos en la ecuación 2, quedando $s_n = 2h_n + \frac{3}{2}h_{n-1}$ y como $h_n + s_n = 2000 \implies 2000 = 3h_n + \frac{3}{2}h_{n-1} \implies h_n = 2000 - \frac{1}{2}h_{n-1}$

### `Ejemplo 4`
> En una flor, tomando cada pétalo como *me quiere* o *no me quiere* quitando solo los *no me quiere* qué número de pétalos queda de último? *(si el problema es difícil, más difícil es que ella te quiera)*

La relación de recurrecia se plantea de la siguiente forma:
1. $a_{2k} = 2a_k - 1$
2. $a_{2k+1} = 2a_k + 1$
3. $a_1 = 1$

Para el caso 1 notemos que si tenemos una cantidad par de pétalos al cabo de una vuelta terminaremos en la misma posición en la que empezamos con *me quiere*, en base a eso si tenemos que la posición resultante con $k$ pétalos es $a_k$, al duplicar los pétalos esta posición se convierte en $2a_k-1$, ya que en la primera vuelta terminaríamos en la primera posición que empezamos.

Para el caso 2 si con $k$ pétalos tenemos que la posición resultante es la $a_k$, entonces al analizar $2k+1$ pétalos, si tenemos en cuenta lo analizado en el caso 1, este pétalo pasaría a ser $2a_k-1$, pero como $2k+1$ es una cantidad impar, después de la primera vuelta no vamos a empezar en el pétalo 1 sino en el 3 (porque al tener una cantidad impar de pétalos, la condición del pétalo 1 y n es *me quiere*, por lo que después de la primera vuelta, el inicial será *no me quiere* y el próximo disponible será el 3ro), por tanto, el sistema queda rotado 2 unidades a favor de las manecillas del reloj, y el pétalo resultante debe ser $2a_k-1+2 \implies 2a_k+1$

### `Ejemplo 5`
> Cómo llenar un tablero de $1$x$n$ con fichas de $1x1$ y $1x2$

La primera forma de hacerlo es equivalente al ejemplo de la escalera $\implies a_n = a_{n-1}+a_{n-2}$

Otra forma es analizando que con fichas de $1x2$ se llenan $2k$ casillas, quedándome $n-2k$ casillas, y como hago $k$ grupos tengo que poner $k$ separadores $\implies (^{n-2k+k}_k)$ con $k$ entre 0 y $\lfloor \frac{n}{2} \rfloor \implies F_{n+1} = \sum^{\lfloor \frac{n}{2} \rfloor}_{k=0}(^{n-k}_k)$

### `Ejemplo 6`
> De cuántas formas se pueden repartir $n$ objetos iguales en $k$ categorías distintas?

Notemos que el problema se puede dividir en dos momentos disjuntos que su unión conforman la solución final, si nos fijamos en un elemento, este puede estar o no en la repartición que hagamos, luego la cantidad de formas de hacer la repartición es en la que no esté el elemento (repartir $n-1$ objetos iguales en $k$ categorías distintas) o en la que esté (repartir $n-1$ objetos iguales en $k-1$ categorías distintas). Por tanto, la recurrencia quedaría de la siguiente forma: $a_{n,k} = a_{n-1,k} + a_{n-1,k-1}$ con $a_{0,2}=1$ y $a_{0,1} = 1$

## Ejercicios

### `Problema 1`
> Expresa una relación de recurrenica que permita calcular:
> 1. El número de palabras de longitud $n$ con letras mayúsculas que no contengan dos $z$ juntas
> 2. El número de cadenas de longitud $n$ sobre $\{a,b,c\}$ con una cantidad impar de $c$

### `1. Solución`
Sea $a_n$ la cantidad de palabras válidas que podemos formar con $n$ caracteres. Notemos que la cantidad de formas en que la palabra comienze con $a$ es $a_{n-1}$ porque los restantes $n-1$ caracteres serán una palabra válida, luego, este mismo análisis se puede hacer con las primeras 25 letras del alfabeto.

Al analizar la $z$ vemos que, el siguiente caracter no puede ser $z$, luego, las dos primeras letras pueden ser $za,zb,\ldots,zy$. Por tanto, la recurrencia tiene la forma:
$$a_n=25a_{n-1}+25a_{n-2}$$

### `2. Solución (1)`
Sea $p_n$ la cantidad de formas de formar cadenas con $n$ caracteres con una cantidad par de $c$ e $i_n$ con una cantidad impar de $c$, y $3^n$ la cantidad total de cadenas. Se cumple que:
$$p_n=2p_{n-1}+i_{n-1}\\
  i_n=2i_{n-1}+p_{n-1}$$

La cantidad de candenas de tamaño $n$ con una cantidad par de $c$ podemos verla como, empezando con $a$ contar una cantidad par de $c$ en las restantes $n-1$ letras, al igual que empezando con $b$. Luego, si empezara con $c$ tendríamos que contar con $n-1$ la cantidad que formas en que tendríamos una cantidad impar de $c$.

Despejando en el sistema llegamos a la fórmula:
$$a_n=4a_{n-1}-3a_{n-2}$$

### `2. Solución (2)`
Notemos que la cantidad de cadenas tamaño $n$ que comienzan con $a$ en $a_{n-1}$, al igual que las que comienzan con $b$. Si comienzan con $c$ hay 3 posibilidades, $ca,cb,cc$, para cada una de las dos primeras es como si quitaramos la segunda letra y hallemos la cantidad de formas para $n-1$ de que comiencen con $c$, que es la cantidad total con $n-1$ menos las que comienzan con $a$ y $b \implies a_{n-1}-2a_{n-2}$, y si comenzara con $cc$ basta eliminarlas y sumar la cantidad de formas con $n-2$. Por tanto, la fórmula final resulta:
$$a_n=4a_{n-1}-3a_{n-2}$$

### `Problema 2`
> Sea $n \in \Z_+$ Calcule el número de formas de descomponer a $n$ en sumandos positivos donde el orden es significativo.

### `Solución`
Sea $a_n$ la cantidad de formas de descomponer a $n$ con las condiciones del problema, luego, si el primero de esos sumandos es 1, al eliminarlo tendríamos la cantidad de formas de descomponer a $n-1$ en sumandos con las condiciones propuestas, si empieza en $k \gt 1$ le restamos uno a $k$ y volveríamos a tener la cantidad de formas de descomponer a $n-1$ en dichos sumandos $\implies$
$$a_n=2a_{n-1}$$

### `Problema 3`
> Una permutación $p_1p_2 \dots p_n$ se llama especial si $\forall i = 1 \to n-1$ existe  $j>i$ tal que $|p_i-p_j|=1$. Calcule el número de permutaciones especiales del conjunto $\{1,2,\dots n\}$

### `Solución`

### `Problema 4`
> Sea $n \in \Z_+$ encuentre una relación de recurrencia para calcular el número de formas de escribir $n$ como suma ordenada de $\Z_+$ de modo que cada sumando sea mayor o igual que $2$

### `Solución`

### `Problema 5`
> Exprese la relación de recurrencia que permite calcular el número de cadenas de longitud $n$ sobre el alfabeto $\{0,1,2\}$ que no contengan $00$ ni $11$

### `Solución`
Sea $x_n$ la cantidad de formas válidas con $n$ caracteres y $a_n,b_n,c_n$ la cantidad que empieza con $0,1,2$ respectivamente, entonces se cumplen las siguientes igualdades:
$$a_n=b_{n-1}+c_{n-1}\\
  b_n=a_{n-1}+c_{n-1}\\
  c_n=a_{n-1}+b_{n-1}+c_{n-1}$$

Notemos que $x_n=a_n+b_n+c_n$ y si sustituimos las igualdades anteriores resulta:
$$x_n=(b_{n-1}+c_{n-1})+(a_{n-1}+c_{n-1})+(a_{n-1}+b_{n-1}+c_{n-1})\\
x_n=2x_{n-1}+c_{n-1}\\
x_n=2x_{n-1}+x_{n-2}$$

### `Problema 6`
> Encuentre la relación de recurrencia que permite calcular el número de permutaciones de $\{1,2,\dots n\}$ donde ningún elemento está en su posición original

### `Solución`
Si analizamos, podemos hacer una biyección entre calcular el número de permutaciones de $n$ elementos donde ninguno esté en su posición y la cantidad de formas de hacer un intercambio de regalos con $n$ personas de forma tal que ninguna se regale a si misma. Vemos las personas como las posiciones de nuestro array y los elementos que ponemos en las posiciones como las personas a las que dicha persona le regala, garantizando que ninguna persona se regale a sí misma estaremos asegurando que en la posición $i$ no esté el elemento $i$ en el array.

Sea $a_{n-1}$ la cantidad de formas de realizar el intercambio de regalos con $n-1$ personas, luego, al añadir una persona esta puede regalarle a cada una de las $n-1$ restantes, y por cada una tenemos dos casos disjuntos, que esta le regale a otra persona o que le regale a la nueva:
1. En caso que la persona regalada le regale a alguna de las $n-2$ restantes podemos ver estas dos personas como una sola, que debe regalar a alguna de las otras $n-2$ (en caso de la persona que está siendo regalada por la nueva) y debe ser regalada (en caso de la persona nueva que solo está regalando), con lo cual tendríamos un intercambio de regalos con nuevamente $n-1$ personas.
2. En caso que la persona regalada le regale a la nueva en ellas se formó un intercambio disjunto del resto, por lo cual, basta en este caso contar la cantidad de formas de hacer un intercambio con las demás $n-2$ personas.

En conclusión, la cantidad de formas de hacer un intercambio de regalos con $n$ personas es:

$$a_n = (n-1)(a_{n-1} + a_{n-2})$$