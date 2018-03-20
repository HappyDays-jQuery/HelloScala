# Array(mutable)

## API
https://www.scala-lang.org/api/current/scala/Array.html

## 配列

https://docs.scala-lang.org/ja/overviews/collections/arrays.html

## ex

### 初期化
```sbt
scala> val arr = Array(1, 2, 3, 4, 5)
arr: Array[Int] = Array(1, 2, 3, 4, 5)
```

### 型の省略なし

```sbtshell
scala> val arr = Array[Int](1, 2, 3, 4, 5)
arr: Array[Int] = Array(1, 2, 3, 4, 5)
```

### 要素絵の代入とアクセス

```sbtshell
scala> arr(0) = 7

scala> arr
res1: Array[Int] = Array(7, 2, 3, 4, 5)

scala> arr(0)
res2: Int = 7
```

### 長さ

```sbtshell
scala> arr.length
res3: Int = 5
```

### 練習

```sbtshell
def swapArray[T](arr: Array[T])(i: Int, j: Int): Unit = {
  val tmp = arr(i)
  arr(i) = arr(j)
  arr(j) = tmp
}
```

```sbtshell
scala> val arr = Array(1, 2, 3, 4, 5)
arr: Array[Int] = Array(1, 2, 3, 4, 5)

scala> swapArray(arr)(0, 4)

scala> arr
res5: Array[Int] = Array(5, 2, 3, 4, 1)

scala> swapArray(arr)(1, 3)

scala> arr
res7: Array[Int] = Array(5, 4, 3, 2, 1)
```
