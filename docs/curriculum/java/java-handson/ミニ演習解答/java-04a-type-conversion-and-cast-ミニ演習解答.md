# Java-04A ミニ演習解答

対象資料: `docs/curriculum/java/java-handson/java-04a-type-conversion-and-cast.md`

## レベル1（基本）解答
変更内容:
- Step 4の `priceText` を `"2500"` に変更

```java
String priceText = "2500";
```

期待出力例:
```text
変換前の価格: 2500
税込金額(double): 2750.0
請求金額(int): 2750
```

---

## レベル2（拡張）解答
変更内容:
- Step 4の `taxRate` を `0.08` に変更

```java
double taxRate = 0.08;
```

期待出力例:
```text
税込金額(double): 1166.4
請求金額(int): 1166
```

`double` から `int` へのキャストでは、小数点以下の `.4` が切り捨てられる。

---

## レベル3（実務）解答
変更内容:
- 数量文字列を数値へ変換し、小計に税率を適用

```java
public class TypeConversionDemo {
    public static void main(String[] args) {
        String priceText = "1080";
        int price = Integer.parseInt(priceText);

        String quantityText = "3";
        int quantity = Integer.parseInt(quantityText);
        int subtotal = price * quantity;

        double taxRate = 0.10;
        double taxedPrice = subtotal * (1 + taxRate);
        int billingAmount = (int) taxedPrice;

        System.out.println("数量: " + quantity);
        System.out.println("小計: " + subtotal);
        System.out.println("請求金額: " + billingAmount);
    }
}
```

期待出力例:
```text
数量: 3
小計: 3240
請求金額: 3564
```

---

## 実行前予想問題の解答
1. `System.out.println((int) 12.9);`
- 出力: `12`

2. `System.out.println(5 + 2.5);`
- 出力: `7.5`

---

## デバッグ演習（任意）の解答
`String` 型の値を `int` 型の変数へ直接代入できないため、`int price = priceText;` はコンパイルエラーになる。

```text
incompatible types: String cannot be converted to int
```

文字列を整数へ変換する `Integer.parseInt(...)` を使用して修正する。

```java
int price = Integer.parseInt(priceText);
```
