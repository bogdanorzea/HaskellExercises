**Exercise 1.4**

How should the definition of the function qsort be modified so that it produces a reverse sorted version of a list?

**Code**
```haskell
reversed_qsort :: Ord a => [a] -> [a]
reversed_qsort []     = []
reversed_qsort (x:xs) = reversed_qsort greater ++ [x] ++ reversed_qsort smaller
                        where greater = [g | g <- xs, g >= x]
                              smaller = [s | s <- xs, s < x]

main = do
  let lst = [2, 5, 6, 8, 7, 45, 234, 64, 5, 43, 4, 536]
  print $ "Reversed quick sort for list " ++ show lst ++ " is: " ++ show (reversed_qsort lst)
```

**Result**
```bash
"Reversed quick sort for list [2,5,6,8,7,45,234,64,5,43,4,536] is: [536,234,64,45,43,8,7,6,5,5,4,2]"
```
