# Teoría de Números 7

## Temas
1. **Teorema de Fermat (demostración)**
2. **Teorema de Wilson**

## Teorema de Fermat (demostración)
Recordemos el Teorema de Fermat.
> Sea $p$ primo, $a \in Z$ y $mcd(a,p) = 1$ entonces se cumple que:
> $$a^{p-1} \equiv 1 \ \ mod(p)$$

Sea $P = \{0,1,\ldots, p-1\}$ un SRC módulo $p$, luego, como $mcd(a,p)=1 \implies$ al multiplicar cada elemento de $P$ por $a$ el resultado será un conjunto $P'$ que seguirá siendo un SRC módulo $p \implies P' = \{0,a,2a,\ldots,(p-1)a\}$

Al multiplicar todos los elementos de $P'$ excepto el cero obtenemos $a*2a*3a*\cdots *(p-1)a \equiv \ 1*2*\cdots *(p-1) \ mod(p) \implies a^{p-1}(p-1)! \equiv (p-1)! \ mod(p)$ y como $p$ es primo entonces es primo relativo con todos los números menores que él $\implies mcd(p,(p-1)!)=1 \implies a^{p-1} \equiv 1 \ mod(p)$

