[![MIT license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/timfame/fp-homework/blob/master/LICENSE)

DSL for my own language\
Examples:\
```haskell
mainFunc = twoArgFunc $ \a1 a2 returnValue -> 
  (##) (22 :: Int) $ \funny ->
  (##) (33 :: Int) $ \scared ->
  funny *= (!!) (555 :: Int) \\
  scared += (!!) (42.2 :: Double) %+% ($$) scared \\
  funny -= (!!) (100 :: Int) \\
    iff (a1 ~=~ ($$) funny ~&&~ a2 ~=~ ($$) scared)
      (returnValue === (!!) (100 :: Int))
      (returnValue === (!!) (-100 :: Int))`

```

```haskell
log2 = oneArgFunc $ \a logCnt ->
  (##) (0 :: Int) $ \accum ->
  accum === (!!) (1 :: Int) \\
  logCnt === (!!) (0 :: Int) \\
  while (a ~>~ ($$) accum)
    ( accum *= (!!) (2 :: Int) \\
      logCnt += (!!) (1 :: Int)
    )
```

To try it, run `stack ghci` and use `runMainFunc` or `runLog2`
