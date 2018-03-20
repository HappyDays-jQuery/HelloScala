# Range (immutable)

## API
http://www.scala-lang.org/api/2.12.4/scala/collection/immutable/Range.html

## ex

```sbtshell
scala> 1 to 5
res8: scala.collection.immutable.Range.Inclusive = Range 1 to 5

scala> (1 to 5).toList
res9: List[Int] = List(1, 2, 3, 4, 5)

scala> 1 until 5
res10: scala.collection.immutable.Range = Range 1 until 5

scala> (1 until 5).toList
res11: List[Int] = List(1, 2, 3, 4)
```
