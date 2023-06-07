# Combinatoria 3

## Temas:
1. **Principio de Inclusión-Exclusión**
2. **Principio del palomar**

## Principio de Inclusión-Exclusión
Siendo $A$ y $B$ dos conjuntos con intersección vacía, entonces la cantidad de elementos en $|A  \cup B|$ es equivalente a $|A| + |B|$. Pero qué ocurriría si no hay garantía de que su intersección fuese vacía? En ese caso al contar $|A| + |B|$ estamos contado doble $|A \cap B|$ por lo que:

> ## $$|A  \cup B| = |A| + |B| - |A \cap B|$$

Esta fórmula se cumple para cualesquiera dos subconjuntos $A$ y $B$, pero y si en lugar de dos conjuntos tengo $3$? Notemos que la cantidad de elementos en $A \cup B \cup C$ es equivalente a contar $|A| + |B| + |C|$ pero $A \cap B, A \cap C, B \cap C$ las estamos contando dobles, ya que al contar $|A|$ estamos contando $|A \cap B$| y $|A \cap C|$ y así análogamente con los otros conjuntos, es decir que debemos restar esas intersecciones, y además, si analizamos la intersección $A \cap B \cap C$ nos damos cuenta que al contar $|A|,|B|,|C|$ y $A \cap B, A \cap C, B \cap C$ en cada una contamos la intersección de los 3, por lo que al restarle a la suma de los elementos en los conjuntos las intersecciones dos a dos eliminamos la intersección, sin embargo nos interesa contarla, por lo que al final debemos añadirla $\implies$

> ## $$|A  \cup B \cup C| = |A| + |B| + |C| - (|A \cap B| + |A \cap C| + |B \cap C|) + |A \cap B \cap C|$$

### `Un elemento en algún conjunto`
Y si ahora quisieramos contar los elementos que están en la unión de $n$ elementos? Sean $A_1, A_2,\ldots,A_m$ subconjuntos de un conjunto universo $U$, entonces se cumple que:

> ## $|A_1 \cup A_2 \cup \ldots \cup A_m| = \sum_{1 \le i \le m}|A_i| - \sum_{1 \le i \lt j \le m}|A_i \cap A_j| + \cdots + (-1)^{m-1}|A_1 \cap A_2 \cap \ldots \cap A_m|$

O podemos verla también de esta forma, buscar la intersección de los complementos de cada conjunto, lo cual sería el universo menos su unión.

### Demostración de la fórmula
Para demostrar la fórmula analicemos los siguientes casos:
1. Los elementos que no cumplen ninguna propiedad: estos elementos no se cuentan, ya que en cada término se cuentan elementos que pertenecen al menos a un conjunto.
2. Los que aparecen solo en un conjunto se cuentan solamente una vez, en algún término $|A_i|$ porque en el resto de término no aparecería.
3. Los que aparecen en $k$ subconjuntos a la vez aparecen en la sumatoria de un subconjunto, en la sumatoria de la intersección de dos subconjuntos y así sucesivamente hasta la sumatoria de las intersecciones de $k$ subconjuntos, porque como aparecen solo en $k$ subconjuntos no aparecen en $k+1$ a la vez, y por tanto en las sumatorias de las intersecciones de $k+1$ subconjuntos esos elementos no son contados. Luego, queda saber cuántas veces se cuenta $k$ en $1,2,\ldots,k$ y esto no es más que $(^k_1) - (^k_2) + \cdots + (-1)^{k-1}(^k_k) = P$. Como ya hemos demostrado en la clase anterior $\sum^n_{k=0}(-1)^k(^n_k) = 0$ y la dejar $(^n_0)$ en un miembro y pasar el resto al otro resulta: $(^n_0) = P \implies P=1$.

Hasta ahora hemos analizado que de un Universo en el que hay $m$ conjuntos puedo saber cuántos elementos pertenecen al menos a un conjunto. Pero y si ahora quisieramos saber cuántos elementos pertenecen a exactamente $k$ subconjuntos.

### `Un elemento en exactamente k conjuntos`
Tengamos en cuenta la siguiente notación: sea $U$ un Universo, $p_1,p_2,\ldots,p_m$ $m$ posibilidades a escoger y $N_{i,j,..}$ la cantidad de elementos que cumplen las propiedades $p_i,p_j,...$. Sea $S_0$ la cardinalidad de $U$ y $S_k$ la suma de las cardinalidades de los elementos que cumplen $k$ propiedades pero contadas de más, o sea, $\sum_{1 \le i_1 \lt i_2 \lt \ldots \lt i_k \le m}N_{i_1,i_2,\ldots,i_k}$.

### Fórmula
Sea $U$ un conjunto finito de $n$ elementos y $P$ un conjunto de $m$ propiedades, entonces los elementos que cumplen exactamente $r$ propiedades son: 

> ## $$N(r)=\sum^{m-r}_{k=0}(-1)^k(^{k+r}_r)S_{k+r}$$

Demostremos que los que cumplen $r$ propiedades se cuentan una vez, y los que cumplen más o menos de $r$ se cuentan cero veces. Analicemos los 3 casos:

### 1. Cumple menos de $r$ propiedades:
Notemos que si el elemento cumple menos de $r$ propiedades la fórmula no lo cuenta porque empieza en $S_r$, o sea, empieza a contar elementos que ya cumplen al menos $r$ propiedades

### 2. Cumple exactamente $r$ propiedades:
Si el elemento cumple exactamente $r$ propiedades solo se cuenta en $S_r$ y da $(^r_r) = 1$

### 3. Cumple más de $r$ propiedades:
Si el elemento cumple $t$ propiedades, con $t \gt r$ ocurre que en $S_{k+r}$ hay $(^t_{k+r})$ formas de repartir $t$ propiedades en grupos de $k+r$, por tanto $N(r)=\sum^{t-r}_{k=0}(-1)^k(^{k+r}_r)(^t_{k+r})$. 

Analicemos ahora $(^{k+r}_r)(^t_{k+r})$ para llevarlo a una forma más simple, pensemos la siguiente situación: tenemos $t$ trabajadores de una empresa y queremos hacer grupos de $k+r$, pero en cada grupo que hagamos queremos saber de cuántas formas podemos seleccionar $r$ delegados para asistir a una reunión, esto es evidente que podemos hacerlo de $(^t_{k+r})(^{k+r}_r)$ formas, lo cual es equivalente a que de los $t$ trabajadores seleccionemos $r$ delegados para asistir a la reunión y de los $t-r$ restantes sacar los grupos de trabajadores que estos representarán en la reunión, y esto puede hacerse de $(^t_r)(^{t-r}_{k})$.

Con la nueva expresión la fórmula quedaría $N(r)=\sum^{t-r}_{k=0}(-1)^k(^t_r)(^{t-r}_{k})$, y como la sumatoria no depende de $r \implies N(r)=(^t_r)\sum^{t-r}_{k=0}(-1)^k(^{t-r}_{k})$ y esta sumatoria da cero *probado en la clase anterior.*

### `Un elemento en al menos k conjuntos`
En este caso como no lo veremos mucho en el curso solo pondremos la fórmula, queda por parte del estudiante ampliar sus conocimientos al respecto.

### Fórmula
> ## $$\overline{N(r)}=\sum^{m-r}_{k=0}(-1)^k(^{k+r-1}_{r-1})S_{k+r}$$

## Principio del Palomar
Este principio es súper evidente, plantea que si tenemos $n$ palomas para colocarlas en $m$ palomares con $n \gt m \implies$ al menos en un palomar habrá más de una paloma.

### `Ejemplo 1`
> En todo grupo de $n$ personas hay dos con la misma cantidad de conocidos.

Supongamos que en el grupo hay una persona que no conoce a nadie y nadie la conoce a ella, tenemos entonces que la cantidad de conocidos de cada una de las restantes $n-1$ personas debe ser un número entre 0 (que no conozca a nadie) y $n-2$ (que conozca a las otras $n-2$ personas), entonces hay $n-1$ posibilidades de conocidos, en caso que sea 0 el número de una de ellas es igual a la primera persona que selecionamos, de lo contrario tendríamos que distribuir $n-2$ posibilidades de conocidos en $n-1$ personas, por lo que a dos personas le tocará la misma cantidad.

Si no hay ninguna persona con cero y como una persona no se conoce a sí misma tendríamos $n$ personas para asignarle a cada una $n-1$ posibles conocidos, y por el *Principio de Palomar* habrá al menos dos con la misma cantidad.

### `Ejemplo 2`
> En un grupo de 6 o más personas hay un trío que se conoce o un trío que no se conoce.

Tomemos una persona, esta puede conocer o no a al menos 3 personas. Supongamos que conoce a 3 personas, entonces esas 3 personas pueden haber 2 que se conozcan, en cuyo caso ya tendremos ellas dos con la primera que se conocen, o que los 3 no se conozcan, y en este caso tenemos el trío de desconocidos.

### `Ejemplo 3`
> En todo conjunto de $n$ números hay un subconjunto cuya suma es múltiplo de $n$.

Sean $a_1,a_2,\ldots,a_n$, analicemos las siguientes sumas:

1. $S_1 = a_1$
2. $S_2 = a_1 + a_2$
3. $S_3 = a_1 + a_2 + a_3$
4. $\cdots$
5. $S_n = a_1 + a_2 + a_+ \cdots + a_n$

Tenemos a repartir en las sumas $n$ posibles restos pero si alguna suma deja resto cero entonces es la suma buscada, de lo contrario tienes $n$ sumas para asignarles $n-1$ restos $\implies$ al menos dos sumas tendrán el mismo resto

## Ejercicios
