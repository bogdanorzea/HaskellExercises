**Exercise 1.4**

Define a function altMap :: (a -> b) -> (a -> b) -> [a] -> [b] that alternately applies its two argument functions to successive elements in a list, in turn about order.

**Code**
```haskell
altMap :: (a -> b) -> (a -> b) -> [a] -> [b]
altMap f g []       = []
altMap f g [x]      = (f x) : []
altMap f g (x:y:ns) = (f x) : (g y) : (altMap f g ns)


main = do
  print $ "altMap (+10) (+100) [0,1,2,3,4] results in: " ++ show (altMap (+10) (+100) [0,1,2,3,4])
```

**Result**
```bash
"altMap (+10) (+100) [0,1,2,3,4] results in: [10,101,12,103,14]"
```
