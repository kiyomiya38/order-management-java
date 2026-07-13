# Java-10 ミニ演習解答

対象資料: `docs/curriculum/java/java-handson/java-10-multi-class-development.md`

## レベル1（基本）解答
`src/service/OrderCalculator.java`の`calcSubtotal(...)`より後へ送料込みメソッドを追加する。

```java
public int calcTotalWithShipping(OrderItem item, int shippingFee) {
    return calcSubtotal(item) + shippingFee;
}
```

`src/app/OrderApp.java`にある既存の`subtotal`の計算と表示を、次の2行へ置き換える。

```java
int billingAmount = calculator.calcTotalWithShipping(item, 800);
System.out.println(item.productName + " 請求額: " + billingAmount);
```

期待出力:
```text
Laptop 請求額: 240800
```

---

## レベル2（拡張）解答
レベル1の`item`、`calculator`、`calcTotalWithShipping(...)`、請求額の表示処理は残し、その後へ次の処理を追記する。

```java
OrderItem mouse = new OrderItem();
mouse.productName = "Mouse";
mouse.quantity = 2;
mouse.unitPrice = 2500;

int laptopSubtotal = calculator.calcSubtotal(item);
int mouseSubtotal = calculator.calcSubtotal(mouse);
int total = laptopSubtotal + mouseSubtotal;

System.out.println(item.productName + " 小計: " + laptopSubtotal);
System.out.println(mouse.productName + " 小計: " + mouseSubtotal);
System.out.println("2件合計: " + total);
```

期待出力:
```text
Laptop 請求額: 240800
Laptop 小計: 240000
Mouse 小計: 5000
2件合計: 245000
```

---

## レベル3（実務）解答
1. `import model.OrderItem;` を外すと、`OrderCalculator` 内の `OrderItem` を解決できず `cannot find symbol` になる。
2. `import model.OrderItem;` を戻して再コンパイルする。
3. `package model;` を `package models;` に変えると、`import model.OrderItem;` と一致しなくなる。
4. `package model;` に戻し、次のコマンドで復旧を確認する。

```bash
javac -encoding UTF-8 -d out src/model/OrderItem.java src/service/OrderCalculator.java src/app/OrderApp.java
java -cp out app.OrderApp
```

---

## レベル4（実務）解答
- `java app.OrderApp` は失敗
- `java -cp . app.OrderApp` も失敗
- `java -cp out app.OrderApp` は成功

`-cp out` は `out` フォルダをクラス探索の起点にする指定。
今回の `.class` は `out/app/OrderApp.class` にあるため、`-cp out` が必要。

---

## 実行前予想問題の解答
Step 4の構成では、必要な行は `1` と `2`。

- `package app;` は `OrderApp` が `app` パッケージに属することを宣言する
- `import service.OrderCalculator;` は別パッケージの `OrderCalculator` を短いクラス名で使うために必要
- `import java.util.List;` はこのプログラムでは `List` を使用しないため不要
