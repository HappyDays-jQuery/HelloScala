# List (immutable)

## API
https://www.scala-lang.org/api/2.12.4/scala/collection/immutable/List.html

## ex

```sbtshell
scala> val lst = List(1, 2, 3, 4, 5)
lst: List[Int] = List(1, 2, 3, 4, 5)
```

Listは一度作成したら値を更新することができません。
```sbtshell
scala> lst(0) = 7
<console>:14: error: value update is not a member of List[Int]
       lst(0) = 7
       ^
```

### Nil：空のList

Scalaで空のListを表すにはNilというものを使います。Rubyなどではnilは言語上かなり特別な意味を持ちますが、Scalaではデフォルトでスコープに入っているということ以外は特別な意味はなく単にobjectです。Nilは単体では意味がありませんが、次に説明する::と合わせて用いることが多いです。

### :: (コンス)

既にあるListの先頭に要素をくっつけるメソッド

```sbtshell
scala> val a1 = 1 :: Nil
a1: List[Int] = List(1)

scala> val a2 = 2 :: a1
a2: List[Int] = List(2, 1)

scala> val a3 = 3 :: a2
a3: List[Int] = List(3, 2, 1)

scala> val a4 = 4 :: a3
a4: List[Int] = List(4, 3, 2, 1)

scala> val a5 = 5 :: a3
a5: List[Int] = List(5, 3, 2, 1)
```


```sbtshell
scala> 1 :: 2 :: 3 :: 4 :: Nil
res13: List[Int] = List(1, 2, 3, 4)
```

```sbtshell
scala> Nil.::(4).::(3).::(2).::(1)
res14: List[Int] = List(1, 2, 3, 4)
```

### ++：List同士の連結

```sbtshell
scala> List(1, 2) ++ List(3, 4)
res15: List[Int] = List(1, 2, 3, 4)

scala> List(1) ++ List(3, 4, 5)
res16: List[Int] = List(1, 3, 4, 5)

scala> List(3, 4, 5) ++ List(1)
res17: List[Int] = List(3, 4, 5, 1)
```

### mkString

文字列のフォーマッティング

#### 引数なし

単にListの各要素を左から順に繋げた文字列を返します。

```sbtshell
scala> List(1, 2, 3, 4, 5).mkString
res20: String = 12345
```

#### mkString(sep: String)

引数にセパレータ文字列sepを取り、Listの各要素をsepで区切って左から順に繋げた文字列を返します。

```sbtshell
scala> List(1, 2, 3, 4, 5).mkString(",")
res22: String = 1,2,3,4,5
```

#### mkString(start: String, sep: String, end: String)

mkString(sep)とほとんど同じですが、startとendに囲まれた文字列を返すところが異なります。

```sbtshell
scala> List(1, 2, 3, 4, 5).mkString("[", ",", "]")
res23: String = [1,2,3,4,5]
```

#### ex.2

```scala
def joinByComma(start: Int, end: Int): String = {
  (start to end).mkString(",")
}
```

```sbtshell
scala> joinByComma(1, 10)
res24: String = 1,2,3,4,5,6,7,8,9,10
```
