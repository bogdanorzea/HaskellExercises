**Exercise 4.8**

The Luhn algorithm is used to check bank card numbers for simple errors such as mistyping a digit, and proceeds as follows:
* consider each digit as a separate number;
* moving left, double every other number from the second last;
* subtract 9 from each number that is now greater than 9;
* add all the resulting numbers together;
* if the total is divisible by 10, the card number is valid. 

Define a function luhnDouble :: Int -> Int that doubles a digit and subtracts 9 if the result is greater than 9. 

Using luhnDouble and the integer remainder function mod, define a function luhn :: Int -> Int -> Int -> Int -> Bool that decides if a four-digit bank card number is valid.

**Code**

```haskell
luhnDouble :: Int -> Int
luhnDouble x 
  | double <= 9 = double
  | otherwise   = double - 9
  where double = 2 * x
  
luhn :: Int -> Int -> Int -> Int -> Bool
luhn a b c d
  | finalSum `mod` 10 == 0 = True
  | otherwise              = False
  where finalSum = sum ([a, b, c, d] ++ [luhnDouble a, b, luhnDouble c, d])

main = do
  print $ "For list 1 7 8 4 the luhn algorithm returns " ++ show (luhn 1 7 8 4)
  print $ "For list 3 7 8 4 the luhn algorithm returns " ++ show (luhn 3 7 8 4)
```

**Result**
```bash
"For lists 1 7 8 4 the luhn algorithm returns True"
"For lists 3 7 8 4 the luhn algorithm returns False"
```

