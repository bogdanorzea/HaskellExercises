**Exercise 6.7**

Define a recursive function merge :: Ord a => [a] -> [a] -> [a] that merges two sorted lists to give a single sorted list.

Note: your definition should not use other functions on sorted lists such as insert or isort, but should be defined using explicit recursion. 

**Code**

```haskell
merge :: Ord a => [a] -> [a] -> [a]
merge [] [] = []
merge xs [] = xs
merge [] ys = ys
merge (x:xs) (y:ys)
  | (x <= y)  = x:(merge xs (y:ys))
  | otherwise = y:(merge (x:xs) ys)

main = do
  print $ "Merging lists [2,5,6] and [1,3,4] will result in:  " ++ show (merge [2,5,6] [1,3,4])
```

**Result**
```bash
"Merging lists [2,5,6] and [1,3,4] will result in:  [1,2,3,4,5,6]"
```
