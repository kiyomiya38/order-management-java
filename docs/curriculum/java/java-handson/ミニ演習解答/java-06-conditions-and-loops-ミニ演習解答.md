# Java-06 ミニ演習解答

対象資料: `docs/curriculum/java/java-handson/java-06-conditions-and-loops.md`

## レベル1（基本）解答
`requestedQuantity` を `10` に変更する。

```java
int requestedQuantity = 10;
```

期待出力:
```text
在庫が不足しています
```

次に `requestedQuantity` を `0` に変更する。

```java
int requestedQuantity = 0;
```

期待出力:
```text
注文数が不正です
```

---

## レベル2（拡張）解答
```java
for (int orderNo = 1; orderNo <= 10; orderNo++) {
    if (orderNo % 2 != 0) {
        continue;
    }
    if (orderNo == 6) {
        break;
    }
    System.out.println("処理対象注文: " + orderNo);
}
```

期待出力:
```text
処理対象注文: 2
処理対象注文: 4
```

---

## レベル3（実務）解答
```java
int stock = 3;

for (int orderNo = 1; orderNo <= 10; orderNo++) {
    if (orderNo == 3) {
        continue;
    }
    if (stock <= 0) {
        System.out.println("在庫終了");
        break;
    }

    System.out.println("処理対象注文: " + orderNo);
    stock--;
}
```

期待出力:
```text
処理対象注文: 1
処理対象注文: 2
処理対象注文: 4
在庫終了
```

---

## 実行前予想問題の解答
表示順: `1`, `3`, `4`

---

## デバッグ演習（任意）の解答
`if requestedQuantity <= 0` は、条件式を囲む丸括弧がないため構文エラーになる。

```java
if (requestedQuantity <= 0) {
```

`if (条件)` の形式へ戻して再コンパイルする。
