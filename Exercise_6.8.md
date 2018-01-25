**Exercise 6.8**

Using merge, define a function msort :: Ord a => [a] -> [a] that implements merge sort, in which the empty list and singleton lists are already sorted, and any other list is sorted by merging
together the two lists that result from sorting the two halves of the list separately. 

Hint: first define a function halve :: [a] -> ([a],[a]) that splits a list into two halves whose lengths differ by at most one.

**Code**

```haskell
halve :: Ord a => [a] -> ([a],[a])
halve [] = ([], [])
halve xs = (take middleIndex xs, drop middleIndex xs)
  where middleIndex = length xs `quot` 2

merge :: Ord a => [a] -> [a] -> [a]
merge [] [] = []
merge xs [] = xs
merge [] ys = ys
merge (x:xs) (y:ys)
  | (x <= y)  = x:(merge xs (y:ys))
  | otherwise = y:(merge (x:xs) ys)

msort :: Ord a => [a] -> [a]
msort [] = []
msort [x] = [x]
msort xs = do let (f, s) = (halve xs) in merge (msort f) (msort s)

main = do
  print $ "The list [1,5,6,2,9] sorted using merge sort is:  " ++ show (msort [1,5,6,2,9])

```

**Result**
```bash
"The list [1,5,6,2,9] sorted using merge sort is: [1,2,5,6,9]"
```
