# Java-12A ミニ演習解答

対象資料: `docs/curriculum/java/java-handson/java-12a-access-modifiers.md`

## レベル1（基本）解答
既存の`Account`クラス内へ、次のフィールドとメソッドだけを追加する。クラス全体は置き換えない。

```java
private int loginFailures = 0;

public void recordFailure() {
    loginFailures++;
}

public int getLoginFailures() {
    return loginFailures;
}
```

`AccountInspector.main(...)`の既存処理の後へ、公開メソッドを利用する次のコードを追記する:

```java
a.recordFailure();
System.out.println("loginFailures: " + a.getLoginFailures());
```

## レベル2（拡張）解答
レベル1の追加は残す。`a.privateInfo()`はprivateメソッドを別クラスから呼び出すためコンパイルエラーになる。確認後は呼び出しを削除する。

## レベル3（実務）解答
レベル1の追加は残す。`InternalRule.value()`を一時的にprivateへ変更する:

```java
package model;

class InternalRule {
    private static String value() {
        return "internal-rule";
    }
}
```

既存の `AccountInspector` 側の呼び出しは、同じパッケージでもprivateメソッドへアクセスするためコンパイルエラーになる:

```java
System.out.println(InternalRule.value());
```

コンパイルエラーを確認したら、`value()`から`private`を外してpackage-privateへ戻す。レベル1で追加したログイン失敗回数の機能は残す。

### レベル3完了時の全コード

`src/model/Account.java`:

```java
package model;

public class Account {
    public String id = "A-001";
    protected int points = 100;
    String status = "ACTIVE";
    private String secret = "internal";
    private int loginFailures = 0;

    public String publicInfo() { return "public"; }
    protected String protectedInfo() { return "protected"; }
    String packageInfo() { return "package-private"; }
    private String privateInfo() { return "private"; }
    public String debugSecret() { return privateInfo() + ":" + secret; }

    public void recordFailure() { loginFailures++; }
    public int getLoginFailures() { return loginFailures; }
}
```

`src/model/InternalRule.java`:

```java
package model;

class InternalRule {
    static String value() {
        return "internal-rule";
    }
}
```

`src/model/AccountInspector.java`:

```java
package model;

public class AccountInspector {
    public static void main(String[] args) {
        Account a = new Account();
        System.out.println(a.id);
        System.out.println(a.points);
        System.out.println(a.status);
        System.out.println(a.publicInfo());
        System.out.println(a.protectedInfo());
        System.out.println(a.packageInfo());
        System.out.println(a.debugSecret());
        System.out.println(InternalRule.value());

        a.recordFailure();
        System.out.println("loginFailures: " + a.getLoginFailures());
    }
}
```
