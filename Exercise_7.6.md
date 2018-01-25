**Exercise 7.6**

Define the higher-order library function curry that converts a function on pairs into a curried function, and, conversely, the function uncurry that converts a curried function with two arguments into a function on pairs.
Hint: first write down the types of the two functions. 

**Code**
```haskell
_curry :: ((a,b) -> c)-> (a -> b -> c)
_curry f = \x y -> f (x, y)

_uncurry :: (a -> b -> c) -> ((a, b) -> c)
_uncurry f = \(x,y) -> f x y


main = do
  print $ "curry fst 2 3 results in: " ++ show (_curry fst 2 3)
  print $ "uncurry mod (5,4) results in: " ++ show (_uncurry mod (5,4))

```

**Result**
```bash
"curry fst 2 3 results in: 2"
"uncurry mod (5,4) results in: 1"
```
