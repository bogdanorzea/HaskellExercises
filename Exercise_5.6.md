**Exercise 5.6**

A positive integer is perfect if it equals the sum of all of its factors, excluding the number itself. 

Using a list comprehension and the function factors, define a function perfects :: Int -> [Int] that returns the list of all perfect numbers up to a given limit.

**Code**

```haskell
factors :: Int -> [Int]
factors n = [x | x <- [1..n], n `mod` x == 0] 

perfects :: Int -> [Int]
perfects n = [x | x <- [1..n], 2 * x == sum (factors x)]


main = do
  print $ "The list of all perfects up to 500 is:  " ++ show (perfects 500)
```

**Result**
```bash
"The list of all perfects up to 500 is:  [6,28,496]"
```
