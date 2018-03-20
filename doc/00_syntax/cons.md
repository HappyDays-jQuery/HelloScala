# :: (cons)

読み方：コンス
おそらく構築（construct)の略
既存のリストの先頭に新しい要素を追加して得られるリストを返す

## ex

```scala
val twoThree = List(2,3)
val oneTwoThree = 1 :: twoThree
plintln(oneTwoThree)
```
> List(1,2,3)

```scala
1 :: twoThree
```
は`twoThree`のメソッド`::`で`1`は`::`の引数
```
twoThree.::(1)
```

以下の様に書くこともできる
```scala
val oneTwoThree = 1 :: 2 :: 3 :: Nil
plintln(oneTwoThree)
```
> List(1,2,3)

※末尾に`Nil`が必要な理由は、`::`が`List`で定義されているからである。
`1 :: 2 :: 3` と書こうとすると、コンパイルエラーになる
`3`は`Int`であり、`::`メソッドを定義されていないため