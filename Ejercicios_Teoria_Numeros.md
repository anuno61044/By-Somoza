# Ejercicios de Teoría de Números

## Problemas

### `Problema 1`
> Sea $p$ primo y $n \in \Z_+^*$. Prueba que existen infinitos múltiplos de $p$ de la forma $2^n-n$.

## Soluciones

### `Solución 1`
Nótese que como $p$ es primo $2^{p-1} \equiv 1 \ mod(p)$, luego, siendo $n$ cualquier múltiplo de $n$ se cumple que $2^n \equiv 1 \ mod (p)$

Probemos que para $n=(p-1)^{2k}$ se cumple la condición del problema:
$$2^{(p-1)^{2k}}-(p-1)^{2k} \equiv 1-(p-1)^{2k} \equiv 1-(-1)^{2k} \equiv 1-1 \ mod(p)$$

Por lo que existen infinitos valores de $k$ para los cuales, al obtener el valor de $n=(p-1)^{2k}$ se cumple que $p \div 2^n-n$