# Java-11A ミニ演習解答

対象資料: `docs/curriculum/java/java-handson/java-11a-constructor-chaining.md`

## レベル1（基本）解答

`User`へ引数なしコンストラクタを追加する。

```java
User() {
    this("guest");
}
```

`main(...)`の既存処理より後へ、生成と表示を追加する。

```java
User guest = new User();
System.out.println(guest.name);
```

`guest`の名前は`guest`になる。

---

## レベル2（拡張）解答
レベル1の引数なしコンストラクタを残し、次を追加・変更する。

```java
String role;

User(String name) {
    this(name, "member");
}

User(String name, String role) {
    this.name = name;
    this.role = role;
}
```

`main(...)`へ生成と表示を追加する。

```java
User member = new User("Tanaka");
System.out.println(member.name + " / " + member.role);
```

期待出力は`Tanaka / member`。

---

## レベル3（実務）解答
レベル2の完成コードで、エラー確認用の変更だけを一時的に行う。
`this(...)` より前へ処理を書くとコンパイルエラーになる。

```java
User(String name) {
    this.name = name;
    this(name, "member");
}
```

`this(...)` はコンストラクタの最初の文にする。
