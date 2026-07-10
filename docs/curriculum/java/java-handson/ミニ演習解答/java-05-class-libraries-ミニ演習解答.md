# Java-05 ミニ演習解答

対象資料: `docs/curriculum/java/java-handson/java-05-class-libraries.md`

## レベル1（基本）解答
Step 3の出力処理に、文字列長の表示を追加する。

```java
System.out.println("trim前 length: " + rawName.length());
System.out.println("trim後 length: " + normalized.length());
```

`price` と `taxRate` を次のように変更する。

```java
int price = 1980;
double taxRate = 0.08;
```

期待出力例:
```text
trim前 length: 13
trim後 length: 9
税込価格(四捨五入): 2138
```

---

## レベル2（拡張）解答
Step 3の `today` と `orderId` を利用して、次の処理を追加する。

```java
LocalDate threeDaysLater = today.plusDays(3);
String secondOrderId = UUID.randomUUID().toString();

System.out.println("3日後: " + threeDaysLater);
System.out.println("UUID-1: " + orderId);
System.out.println("UUID-2: " + secondOrderId);
```

確認ポイント:
- `threeDaysLater` は実行日の3日後になる
- `orderId` と `secondOrderId` は通常、異なる値になる

---

## レベル3（実務）解答
```java
String businessOrderId = "ORD-" + orderId;
System.out.println(today + " / " + businessOrderId);
```

期待出力例:
```text
2026-05-29 / ORD-123e4567-e89b-12d3-a456-426614174000
```

日付とUUID部分は実行するたびに変わる。

---

## 実行前予想問題の解答
1. `"  ABC  ".trim().length()` -> `3`  
2. `"ABC".length()` -> `3`

---

## デバッグ演習（任意）の解答
`import java.time.LocalDate;` を外すと、`LocalDate` の場所を解決できず、`cannot find symbol` が表示される。

確認する内容:
- エラーに `symbol: class LocalDate` が含まれている
- `LocalDate` を使用している行がエラー位置として表示されている

`import java.time.LocalDate;` を戻して再コンパイルすれば解消する。
