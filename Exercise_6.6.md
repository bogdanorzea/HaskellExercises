**Exercise 6.6**

Define the following library functions on lists using recursion:
* Decide if all logical values in a list are True: and :: [Bool] -> Bool 
* Concatenate a list of lists: concat :: [[a]] -> [a]
* Produce a list with n identical elements: replicate :: Int -> a -> [a]
* Select the nth element of a list: (!!) :: [a] -> Int -> a 
* Decide if a value is an element of a list: elem :: Eq a => a -> [a] -> Bool

**Code**
```haskell
_and :: [Bool] -> Bool
_and []     = True
_and (x:xs) = x && _and xs

_concat :: [[a]] -> [a]
_concat []     = []
_concat (x:xs) = x ++ _concat xs

_replicate :: Int -> a -> [a]
_replicate 0 _ = []
_replicate n x = x : _replicate (n-1) x

_nth :: [a] -> Int -> a
_nth (x:xs) 0 = x
_nth (x:xs) i = _nth xs (i-1)

_elem :: Eq a => a -> [a] -> Bool
_elem _ [] = False
_elem a (x:xs)
  | x==a      = True
  | otherwise = _elem a xs


main = do
  print $ "Applying and on list [True, True, False] results in: " ++ show (_and [True, True, False])
  print $ "Concatenating [[1, 2], [3, 4, 5]] results in: " ++ show (_concat [[1, 2], [3, 4, 5]])
  print $ "Replicating 8 times number '5' results in: " ++ show (_replicate 8 5)
  print $ "Element with index 5 in list [1, 2, 3, 4, 5, 6] is: " ++ show (_nth [1, 2, 3, 4, 5, 6] 5)
  print $ "Element 5 is in list [1, 2, 3, 4, 5, 6] is: " ++ show (_elem 5 [1, 2, 3, 4, 5, 6])
```

**Result**
```bash
"Applying and on list [True, True, False] results in: False"
"Concatenating [[1, 2], [3, 4, 5]] results in: [1,2,3,4,5]"
"Replicating 8 times number '5' results in: [5,5,5,5,5,5,5,5]"
"Element with index 5 in list [1, 2, 3, 4, 5, 6] is: 6"
"Element 5 is in list [1, 2, 3, 4, 5, 6] is: True"
```
