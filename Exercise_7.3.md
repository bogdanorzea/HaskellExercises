**Exercise 7.3**

Redefine the functions map f and filter p using foldr.

**Code**
```haskell
_map :: (a -> b) -> [a] -> [b]
_map f []     = []
_map f (x:xs) = foldr (\x xs -> f x:xs) [] (x:xs)

_filter :: (a -> Bool) -> [a] -> [a]
_filter f []     = []
_filter f (x:xs) = foldr (\x xs -> if f x then x:xs else xs) [] (x:xs)

main = do
  print $ "Mapping (+1) on the list [1, 2, 3] results in: " ++ show (_map (+1) [1, 2, 3])
  print $ "Filter (>2) on the list [1, 2, 3] results in: " ++ show (_filter (>2) [1, 2, 3])
```

**Result**
```bash
"Mapping (+1) on the list [1, 2, 3] results in: [2,3,4]"
"Filter (>2) on the list [1, 2, 3] results in: [3]"
```
