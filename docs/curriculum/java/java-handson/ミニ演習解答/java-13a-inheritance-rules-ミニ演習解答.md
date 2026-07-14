# Java-13A ミニ演習解答

対象資料: `docs/curriculum/java/java-handson/java-13a-inheritance-rules.md`

## レベル1（基本）解答
Step 3の`Manager`内にある次のコメントを外す:

```java
class Manager extends Worker {
    @Override
    void submitReport() { }
}
```

`Worker.submitReport()`は`final`メソッドなのでコンパイルエラーになる。確認後はこのメソッドを再びコメントアウトし、Step 3がコンパイルできる状態へ戻す。

## レベル2（拡張）解答
レベル1の確認用変更を戻した後、Step 3にある次のコメントを外す:

```java
class DerivedRole extends FixedRole {
}
```

`FixedRole`は`final`クラスなのでコンパイルエラーになる。確認後は`DerivedRole`を再びコメントアウトしてからレベル3へ進む。

## レベル3（実務）解答
通常の拡張として、既存の`Worker.submitReport()`から`final`を外す:

```java
class Worker {
    void submitReport() { System.out.println("report submitted"); }
}
```

続いて、レベル1では確認後にコメントアウトした`Manager.submitReport()`を正式な実装として有効にする:

```java
class Manager extends Worker {
    @Override
    void submitReport() { System.out.println("manager report submitted"); }
}
```
