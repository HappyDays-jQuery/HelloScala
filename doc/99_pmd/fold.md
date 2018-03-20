## Replace fold with sum less... (⌘F1) 

Replaces fold and reduce methods with sum, product, max or min if possible.

Before:
```scala
List(1, 2, 3).foldLeft(1){(x,y) => x * y}
List(1, 2, 3).fold(0)(_ + _)
List(1, 2, 3).reduce(_ + _)
List(1, 2, 3).reduceLeft(_ min _)
List(1, 2, 3).reduce((x, y) => math.max(x, y))
```

 After:
```scala
List(1, 2, 3).product
List(1, 2, 3).sum
List(1, 2, 3).sum
List(1, 2, 3).min
List(1, 2, 3).max
```
