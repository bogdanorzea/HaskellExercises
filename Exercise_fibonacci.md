**Exercise fibonnaci**

Identify element at position 100 in the Fibonacii sequence.

**Code**
```haskell
fib :: [Integer]
fib = 1 : 1 : [a + b | (a, b) <- zip fib (tail fib)]

main = do
  print $ "Element at position 100 in fibonacci sequence is: " ++ show (fib !! 100)
```

**Result**
```bash
"Element at position 100 in fibonacci sequence is: 573147844013817084101"
```
