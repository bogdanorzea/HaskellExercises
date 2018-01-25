**Exercise Reversed Insertion Sort**

How should the definition of the function insert_sort be modified so that it produces a reverse sorted version of a list?

**Code**
```haskell
reversed_insert :: Ord a => a -> [a] -> [a]
reversed_insert x [] = [x]
reversed_insert x (y:ys) 
  | x >= y = x : y : ys
  | otherwise = y : (reversed_insert x ys)


reversed_insertion_sort :: Ord a => [a] -> [a]
reversed_insertion_sort [] = []
reversed_insertion_sort (x:xs) = reversed_insert x (reversed_insertion_sort xs)

main = do
  print $ "Reversed insertion sort for list [2,5,6,8,7,1] is: " ++ show (reversed_insertion_sort [2,5,6,8,7,1])
```

**Result**
```bash
"Reversed insertion sort for list [2,5,6,8,7,1] is: [8,7,6,5,2,1]"
```
