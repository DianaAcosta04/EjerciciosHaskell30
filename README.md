# EjerciciosHaskell30

## Validación de Números de Tarjetas de Crédito

## Ejercicio 1. 
### Se definen las funciones "toDigits" y "toDigitsRev" para convertir números enteros positivos en una lista de dígitos.

```haskell

toDigits n | n <= 0 = [] | otherwise = map (\x -> read [x] :: Integer) (show n)
toDigitsRev n = reverse (toDigits n)

```
