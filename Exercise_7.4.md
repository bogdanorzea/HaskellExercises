**Exercise 7.4**

Using foldl, define a function dec2Int :: [Int] -> Int that converts a decimal number into an integer. 

**Code**
```haskell
dec2Int :: [Int] -> Int
dec2Int xs = foldl (\x y -> 10 * x +  y) 0 xs

main = do
  print $ "Decimal [2, 3, 4, 5] to int is: " ++ show (dec2Int [2,3,4,5])
```

**Result**
```bash
"Decimal [2, 3, 4, 5] to int is: 2345"
```
