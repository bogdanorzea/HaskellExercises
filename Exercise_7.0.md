**Exercise 7.0**

Using altMap, define a function luhn :: [Int] -> Bool that implements the Luhn algorithm from the exercises in chapter 4 for bank card numbers of any length. 

**Code**

```haskell
ltMap :: (a -> b) -> (a -> b) -> [a] -> [b]
altMap f g []       = []
altMap f g [x]      = (f x) : []
altMap f g (x:y:ns) = (f x) : (g y) : (altMap f g ns)

luhnDouble :: Int -> Int
luhnDouble x 
  | double <= 9 = double
  | otherwise   = double - 9
  where double = 2 * x
  

luhn :: [Int] -> Bool
luhn xs = sum (altMap (+0) luhnDouble (reverse xs)) `mod` 10 == 0

main = do
  print $ "Card number 4485 8234 8090 9390 respects Luth algorithm: " ++ show (luhn [4,4,8,5,8,2,3,4,8,0,9,0,9,3,9,0])
```

**Result**
```bash
"Card number 4485 8234 8090 9390 respects Luth algorithm: True"
```
