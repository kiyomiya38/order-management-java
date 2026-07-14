# Java-12 ミニ演習解答

対象資料: `docs/curriculum/java/java-handson/java-12-encapsulation.md`

## レベル1（基本）解答
Step 3の`EncapsulationDemo`にある呼び出し値だけを一時的に変更する:

```java
account.setUsername("   "); // 一時的な確認値
```

`username は必須です`という例外を確認したら、次の正常値へ戻してレベル2へ進む:

```java
account.setUsername("  Yamada  ");
```

## レベル2（拡張）解答
レベル1で戻した正常なユーザー名はそのままにし、年齢の呼び出し値だけを一時的に変更する:

```java
account.setAge(130); // 一時的な確認値
```

`age の範囲が不正です`という例外を確認したら、Step 3の正常値`30`へ戻してレベル3へ進む。

## レベル3（実務）解答
レベル1・2で確認した既存の検証処理を残したまま、`UserAccount`へ次のコードを追記する:

```java
// レベル3で追記
private String email;

public void setEmail(String email) {
    if (email == null || !email.contains("@")) {
        throw new IllegalArgumentException("email 形式が不正です: " + email);
    }
    this.email = email;
}

public String getEmail() {
    return email;
}
```

`EncapsulationDemo`の既存表示処理の後へ、次のコードを追記する:

```java
// レベル3で追記
account.setEmail("user@example.com");
System.out.println("email: " + account.getEmail());
```
