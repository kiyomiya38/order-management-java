# Java-14 ミニ演習解答

対象資料: `docs/curriculum/java/java-handson/java-14-advanced-inheritance.md`

## レベル1（抽象クラス）解答
```java
class CashPaymentService extends PaymentService {
    @Override
    String getPaymentName() {
        return "現金";
    }
    @Override
    int calculateFee(int amount) {
        return 0;
    }
}
```

`main(...)`で`PaymentService cash = new CashPaymentService();`を生成し、`cash.pay(5000, consoleNotifier);`を呼ぶ。

## レベル2（インターフェース）解答
レベル1の`CashPaymentService`は残し、次の通知クラスを追加する。
```java
class ReceiptNotifier implements Notifier {
    @Override
    public void notifyResult(String message) {
        System.out.println("領収書: " + message);
    }
}
```

`Notifier notifier = new ReceiptNotifier();`を生成し、`card.pay(5000, notifier);`を呼ぶ。

## レベル3（抽象クラスの必要性を確認）解答
レベル2の完成コードから`CashPaymentService.calculateFee(...)`を削除すると、抽象メソッドの実装が不足するためコンパイルエラーになる。確認後はレベル1で追加した実装へ戻す。
