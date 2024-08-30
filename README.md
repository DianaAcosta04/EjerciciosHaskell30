# EjerciciosHaskell30

## Validación de Números de Tarjetas de Crédito

# Ejercicio 1. 
### Se definen las funciones "toDigits" y "toDigitsRev" para convertir números enteros positivos en una lista de dígitos.

```haskell

toDigits n | n <= 0 = [] | otherwise = map (\x -> read [x] :: Integer) (show n)
toDigitsRev n = reverse (toDigits n)

```
### show n convierte el número en una cadena (por ejemplo, 1234 a "1234").
### map (\x -> read [x] :: Integer) aplica una función a cada carácter de la cadena, convirtiéndolo en un Integer.
### (\x -> read [x] :: Integer) convierte un carácter como '1' en el número 1.

# Ejercicio 2
### Define la función `doubleEveryOther` para duplicar cada otro número comenzando desde la derecha.

``` haskell

 doubleEveryOther xs = reverse (zipWith (*) (cycle [1, 2]) (reverse xs))

```
### reverse xs: Invierte la lista para empezar a duplicar desde la derecha.
### zipWith (*) (cycle [1, 2]) (reverse xs): Combina los elementos de la lista invertida con una lista infinita alternada de 1 y 2 ([1, 2, 1, 2, ...]). Esto multiplica cada segundo elemento por 2.
### reverse: Se aplica nuevamente para devolver la lista al orden original.

# Ejercicio 3
### Define la función `sumDigits` para calcular la suma de todos los dígitos.

``` haskell

toDigits n | n <= 0 = [] | otherwise = map (read . (:[])) (show n)
sumDigits xs = sum (concatMap toDigits xs)

```
### toDigits n: Convierte un número en una lista de sus dígitos.
### concatMap toDigits xs: Aplica toDigits a cada elemento de la lista xs y concatena todas las listas de dígitos resultantes.
### sum: Suma todos los digitos.

# Ejercicio 4
### Define la función `validate` para indicar si un número entero podría ser un número de tarjeta de crédito válido.

``` haskell

toDigits n | n <= 0 = [] | otherwise = map (read . (:[])) (show n)
doubleEveryOther xs = reverse (zipWith (*) (cycle [1, 2]) (reverse xs))
sumDigits xs = sum (concatMap toDigits xs)
validate n = (sumDigits (doubleEveryOther (toDigits n))) `mod` 10 == 0


```
### En este ejercicio se reutilizan las funciones que se crearon en los ejercicios anteriores, por ende si se realiza la ejecución en la consola paso por paso desde el ejercicio 1 se pueden reutilizar las funciones anteriores y así permite que la función "Validate" valide si la tarjeta de crédito tiene un número válido
