**Exercise 5.1**

Using a list comprehension, give an expression that calculates the sum 1<sup>2</sup> + 2<sup>2</sup> + ... 100<sup>2</sup> of the first one hundred integer squares.

**Code**
```haskell
main = do
  print $ "The sum of squares of the first 100 integers is:  " ++ show (sum [ x^2 | x <- [0..100]])
```

**Result**
```bash
"The sum of squares of the first 100 integers is:  338350"
```
