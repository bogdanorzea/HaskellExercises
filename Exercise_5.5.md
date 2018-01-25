**Exercise 5.5**

A triple (x, y, z) of positive integers is Pythagorean if it satisfies the equation x<sup>2</sup> + y<sup>2</sup> = z<sup>2</sup>. 
Using a list comprehension with three generators, define a function pyths :: Int -> [(Int,Int,Int)] that returns the list of all such triples whose components are at most a given limit. 


**Code**
```haskell
pyths :: Int -> [(Int,Int,Int)]
pyths n = [(x, y, z)| x <- [1..n], y <- [1..n], z <- [1..n], x^2 + y^2 == z^2]

main = do
  print $ "The triple of Pythagorean numbers smaller than 10 is: " ++ show (pyths 10)
```

**Result**
```bash
"The triple of Pythagorean numbers smaller than 10 is: [(3,4,5),(4,3,5),(6,8,10),(8,6,10)]"
```
