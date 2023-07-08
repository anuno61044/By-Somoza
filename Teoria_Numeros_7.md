# Teoría de Números 7

## Temas
1. **Teorema de Fermat (demostración)**
2. **Teorema de Wilson (demostración)**
3. **Función aritmética**
4. **Sistema Reducido de Restos**
5. **Teorema de Euler**
6. **Funciones multiplicativas**
7. **Función $\varphi(n)$**
8. **Orden $a$ módulo $n$**

## Teorema de Fermat (demostración)
Recordemos el Teorema de Fermat:
> Sea $p$ primo, $a \in Z$ y $mcd(a,p) = 1$ entonces se cumple que:
> $$a^{p-1} \equiv 1 \ \ mod(p)$$

Sea $P = \{0,1,\ldots, p-1\}$ un SRC módulo $p$, luego, como $mcd(a,p)=1 \implies$ al multiplicar cada elemento de $P$ por $a$ el resultado será un conjunto $P'$ que seguirá siendo un SRC módulo $p \implies P' = \{0,a,2a,\ldots,(p-1)a\}$

Al multiplicar todos los elementos de $P'$ excepto el cero obtenemos $a*2a*3a*\cdots *(p-1)a \equiv \ 1*2*\cdots *(p-1) \ mod(p) \implies a^{p-1}(p-1)! \equiv (p-1)! \ mod(p)$ y como $p$ es primo entonces es primo relativo con todos los números menores que él $\implies mcd(p,(p-1)!)=1 \implies a^{p-1} \equiv 1 \ mod(p)$

## Teorema de Wilson (demostración)
Recordemos el Teorema de Wilson:
> Sea $p \in \N$. Se cumple que $p$ es primo $\iff p \div (p-1)!+1$

### `Demostración`
- $\impliedby$

Sea $p \div (p-1)!+1$ y supongamos que existe $d \div p$ tal que $1 \lt d \lt p \implies d \div (p-1)!$ pero $d$ no divide a 1 por tanto $d$ no divide a $(p-1)!+1$, de donde $d=1$ o $d=p$ \implies p$ es primo

- $\implies$

Sea $P=\{1,2,\ldots ,p-1\}$ un SRC exceptuando el cero, nótese que cada elemento posee un inverso módulo $p$ distinto en el conjunto $P$ porque cada $a \in P$ cumple que $mcd(a,p)=1$. Analicemos el caso en que un elemento sea su mismo inverso:
$$a^2 \equiv 1 \ mod(p)\\
(a+1)(a-1) \equiv 0\ mod(p)$$

De donde $a=1$ o $a=p-1$, por lo que en el conjunto $\{2,3,\ldots ,p-2\}$ cada número posee un inverso distinto de él mismo, por lo que se cumple que:
$$2*3*\cdots *(p-2) \equiv 1\ mod(p)\\
2*3*\cdots *(p-2)*(p-1) \equiv (p-1)\ mod(p)\\
(p-1)! \equiv -1\ mod(p)\\
(p-1)! + 1 \equiv 0\ mod(p)$$

Que es lo que queríamos demostrar

## Función aritmética
> Una función es aritmética si está definida en $\Z_+$

Sea $\varphi(n)$ una función aritmética que retorna la cantidad de números menores que $n$ que son coprimos con $n$

## Sistema Reducido de Restos
> Sistema reducido de restos módulo $m$ es un conjunto de $\varphi(m)$ enteros positivos que son primos relativos con $m$, de modo que todo par de ellos es incongruente módulo m.

Si $r_1, r_2,\ldots,r_{\varphi(n)}$ es un sistema reducido de restos módulo $n$ y $a$ es un entero
positivo tal que $mcd(a,n)=1$, entonces $ar_1,ar_2,\ldots, ar_{\varphi(n)}$ también es un sistema
reducido de restos módulo $n$.

### `Demostración`
Debemos demostrar que los $ar_1,ar_2,\ldots, ar_{\varphi(n)}$ son distintos modularmente y primos relativos con $n$.

- Supongamos que para algún $r_k$ se cumple que $mcd(n,ar_k)=d \gt 1 \implies$ existe $p$ primo tal que $p \div n$ y $p \div ar_k$ pero como $mcd(a,n)=1 \implies p \div r_k$ contradicción porque $mcd(n,r_k)=1$
- Supongamos que para algún $i,j$ se cumple que $ar_i \equiv ar_j \ mod(n)$, luego, como $mcd(a,n)=1 \implies$ $r_i \equiv r_j \ mod(n)$ contradicción porque $r_i,r_j$ pertenecen a un SRR

## Teorema de Euler
> Sean $a,n \in \Z_+$, si se cumple que $mcd(a,n)=1 \implies a^{\varphi(n)} \equiv 1 \ mod(n)$

### `Demostración`
Sea $r_1, r_2,\ldots,r_{\varphi(n)}$ un SRR módulo $n$, entonces se cumple que al multiplicarlo por $a$ tal que $mcd(a,n)=1$ también tenemos otro SRR y por tanto:
$$(ar_1)(ar_2)\cdots (ar_{\varphi(n)}) \equiv r_1 r_2\cdots r_{\varphi(n)} \ mod(n)\\
a^{\varphi(n)}r_1 r_2\cdots r_{\varphi(n)} \equiv r_1 r_2\cdots r_{\varphi(n)} \ mod(n)$$

Y como cada $r_i$ es coprimo con $n$ por propiedad de SRR entonces concluimos que:
$$a^{\varphi(n)} \equiv 1 \ mod(n)$$

## Funciones multiplicativas
> Una función aritmética es multiplicativa si $\forall n,m \in \Z$ primos relativos se cumple que $f(nm) = f(n)*f(m)$.

> Una función aritmética es totalmente multiplicativa si $\forall n,m \in \Z$ se cumple que $f(nm) = f(n)*f(m)$.

> Si $f$ es multiplicativa y $n=p_1^{e_1}p_2^{e_2}\cdots p_k^{e_k}$ con $p_i$ primos se cumple que $f(n) = f(p_1^{e_1})*f(p_2^{e_2})*\cdots f(p_k^{e_k})$

## Función $\varphi(n)$
> La función $\varphi(n)$ es mutiplicativa

Para demostrar este teorema haremos uso de los siguientes lemas:

> **Lema 1:**
> 
> Sean $a,b,m \in \N \implies$ se cumple que $mcd(ab,m) = 1 \iff mcd(a,m)=1$ y $mcd(b,m)=1$

La demostración en el sentido $\impliedby$ es obvia. En el otro caso, supongamos que no se cumple, sin pérdida de generalidad sea $mcd(a,m)=d \gt 1 \implies \exist \ p$ primo tal que $p \div m$ y $p \div a \implies p\div ab \implies p\div mcd(ab,m)$ contradicción porque $mcd(ab,m)=1$

> **Lema 2:**
>
> Sean $a,b \in \Z_+^*$ coprimos, entonces se cumple que $mcd(ax,b)=1 \iff mcd(x,b)=1$

$(\implies)$ Supongamos que $mcd(ax,b)=1$ y $mcd(x,b)=d \gt 1 \implies  \exist \ p$ primo tal que $p \div b$ y $p \div x \implies p \div ax \implies p \div mcd(ax,b)$ contradicción porque $mcd(ax,b)=1$. Por tanto $d=1$

$(\impliedby)$ Supongamos que $mcd(x,b)=1$ y $mcd(ax,b)=d \gt 1 \implies  \exist \ p$ primo tal que $p \div b$ y $p \div ax$, pero como $mcd(a,b)=1 \implies p \div x$ porque $p$ no puede dividir a $a$. Luego $p \div mcd(b,x)=1$ contradicción, por lo que $d=1$

> **Lema 3:**
> 
> Sean $k,l \in \Z_+^*$ coprimos. Si $x$ y $y$ recorren respectivamente sistemas completos de restos módulos $k$ y $l$, entonces $xl+yk$ recorre un sistema completo de restos módulo $kl$

No es díficil ver que existen exactamente $kl$ números de la forma $xl+yk$. Supongamos que $xl+yk$ no recorre el sistema completos de restos módulo $kl$, entonces:
$$x_1l+y_1k \equiv x_2l+y_2k \ mod(kl)$$

Por propiedades de congruencia se cumple que:
$$x_1l+y_1k \equiv x_2l+y_2k \ mod(k)\\
x_1l \equiv x_2l \ mod(k)$$

Como $mcd(k,l)=1$ entonces:
$$x_1 \equiv x_2 \ mod(k)$$

Contradicción porque $x$ recorre un SRC módulo $k$. Análogamente se hace el análisis con $l$

> **Lema 4:**
>
> Sean $a,n \in \N$. Se cumple que $mcd(a,n)=1 \iff mcd(x,n)=1$ siendo $a \equiv x \ mod(n)$

Nótese que ambas expresiones son análogas, ya que $a \equiv x \ mod(n)$ es equivalente a $x \equiv a \ mod(n)$ por lo que basta demostrar en un solo sentido de la doble implicación.

Supongamos que dado $mcd(a,n)=1$ se cumpe que $mcd(x,n)=d \gt 1 \implies  \exist \ p$ primo tal que $p \div x$ y $p \div n$ pero como  $a \equiv x \ mod(n)$ se cumple que $n \div (a-x) \implies p \div (a-x)$ y como $p \div x \implies p \div a \implies p \div mcd(a,n)=1$ contradicción porque $mcd(a,n)=1$

### `Demostración (Somoza)`
Agrupemos los números desde 1 hasta $mn$ de la siguiente forma:

$$
\begin{matrix}
1 & m+1 & 2m+1 & \cdots & (n-1)m+1\\
2 & m+2 & 2m+2 & \cdots & (n-1)m+2\\
\cdots &\cdots &\cdots &\cdots &\cdots\\
m & 2m & 3m & \cdots & nm
\end{matrix}
$$

Según el **Lema 1** para saber cuántos números hay coprimos con $mn$ basta calcular cuántos números son coprimos con $m$ y coprimos con $n$ simultáneamente.

Nótese que en una fila, si un elemento deja resto $k$ módulo $m$ entonces todos los elementos de esa fila dejan resto $k$ módulo $n$

Por cada columna tenemos un SRC módulo $m$, en el cual hay $\varphi(m)$ números primos relativos con $m$, ya que su resto módulo $m$ es primo relativo con $m$

Analicemos ahora las filas, nótese que si tenemos un SRC módulo $n$, al multiplicarlo por $m$, como son coprimos seguiremos teniendo un SRC, y al sumarle una constante $k$ igual el resultado será un SRC, luego, si en la matriz buscamos en la fila $k$ observamos que es exactamente lo que tenemos, por lo cual, en cada fila de la matriz hay un SRC módulo $n$, en el cual hay $\varphi(n)$ números primos relativos con $n$

Por último, como tenemos en cada columna $\varphi(m)$ coprimos con $m$ y en cada fila $\varphi(n)$ primos relativos con $n$, la cantidad total de números coprimos con $m$ y $n$ a la vez son $\varphi(m) \varphi(n)$

### `Demostración (Temas escogidos de Teoría de Números)`
Sean $a$ y $b$ enteros positivos coprimos. Supongamos que $x$ y $y$ recorren sistemas completos de restos módulos $a$ y $b$ respectivamente. Por el **Lema 3** $xb+ya$ recorre un sistema completo de restos módulo $ab$, luego aplicando el **Lema 1** y **Lema 2** se cumple que:
$$(xb+ya,ab) = 1 \iff (xb+ya,a) = 1, (xb+ya,b) = 1 \iff (xb,a) = 1, (ya,b) = 1 \iff (x,a) = 1, (y,b) = 1$$

Esto significa que $xb + ya$ es primo relativo con $ab$ si y solo si $x$ es coprimo con $a$ y $y$ es primo relativo con $b$, entonces
$\varphi(ab) = \varphi(a)\varphi(b)$

### `Demostración (Youtube)`
Queremos probar que la función $\varphi(n)$ es multiplicativa, o sea, $\varphi(mn)=\varphi(m)\varphi(n)$.

Sean $M = \{m_1,m_2,\ldots,m_p\}$ y $N=\{n_1,n_2,\ldots,n_q\}$ los sistemas de restos reducidos de $m$ y $n$ respectivamente. Si hallamos una función $f$ biyectiva entre el producto cartesiano de ambos conjuntos y los números que son primos relativos con $mn$ menores que $mn$ habríamos demostrado que la cardinalidad tanto del producto cartesiano ($\varphi(m)\varphi(n)$) como la de $\varphi(mn)$ son iguales.

Apoyándonos en el **Lema 1** y **Lema 4** basta encontrar todos restos primos relativos con $m$ y con $n$ y los números que cumplen con esos restos simultáneamente, por lo que serán coprimos con $mn$, por tanto, nuestra función $f$ será sobreyectiva. Utilizando el *Teorema Chino del Resto* dados $m_i,n_j$ restos de $m,n$ respectivamente, como $mcd(m,n)=1 \implies$ el sistema de congruencia:
$$x \equiv m_i \ mod(m)\\
  x \equiv n_j \ mod(n)$$

Tiene solución y es única, por tanto, garantizamos que la función $f$ es total (abarca todos los elementos del producto cartesiano de ambos conjuntos) y es inyectiva (porque la solución proporcionada por el *Teorema Chino del Resto* es única). Por tanto, podemos concluir que la función $f$ es biyectiva, lo que implica que el producto cartesiano tiene tantos elementos como coprimos menores que $mn \implies \varphi(mn)=\varphi(m)\varphi(n)$

### Expresión de $\varphi(n)$
> Sean $p,k \in \Z_+$ con $p$ primo. Se cumple que:
> $$\varphi(p^k)=p^k(1-\frac{1}{p})$$

Nótese que los números menores que $p^k$ coprimos con este son los que no contienen ningún factor $p$ por tanto, como $p^k=p(p^{k-1})$ entonces en los primeros $p^k$ números hay $p^{k-1}$ números que contienen un factor $p \implies \varphi(p^k)=p^k-p^{k-1}=p^k(1-\frac{1}{p})$ 

> Sea $n \in \Z$ con $n \ge 2$ y $n=p_1^{e_1}p_2^{e_2}\cdots p_k^{e_k}$ entonces se cumple que:
> $$\varphi(n)=n(1-\frac{1}{p_1})(1-\frac{1}{p_2})\cdots (1-\frac{1}{p_k})$$

## Orden $a$ módulo $n$
### `Definición`
> Sea $a,n \in \Z_+$ y $mcd(a,n)=1$. El menor entero positivo $k$ tal que $a^k \equiv 1 \ mod(n)$ se llama orden de $a$ módulo $n$ y se denota $ord_na$

### `Propiedad`
> Sea $a,n \in \Z_+$,$mcd(a,n)=1$ y $ord_na=e \implies a^t \equiv 1 \ mod(n) \iff e \div t$

