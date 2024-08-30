# Torres de Hanoi 

# Ejercicio 5

## Define la función hanoi que devuelve una lista de movimientos a realizar para mover la pila de discos desde la primera estaca hasta la segunda.

``` haskell

hanoi n a b c = if n == 0 then [] else hanoi (n-1) a c b ++ [(a, b)] ++ hanoi (n-1) c b a

```


