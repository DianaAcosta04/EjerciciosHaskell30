# EjerciciosHaskell30

## Validación de Números de Tarjetas de Crédito

## Ejercicio 1. 

```haskell

toDigits n | n <= 0 = [] | otherwise = map (\x -> read [x] :: Integer) (show n)
toDigitsRev n = reverse (toDigits n)

```
