# Java ハンズオン（分割版）

関連資料:
- [Java初学者 -> Spring Boot 実務導入ロードマップ](../../java-to-springboot-roadmap.md)
- [カリキュラム評価ガイド](../../curriculum-assessment-guide.md)
- [Java研修 講師事前チェック](./INSTRUCTOR_CHECKLIST.md)

## 実行環境
- この教材のコマンドは Git Bash で実行する前提
- `mkdir -p`、`~/order-management-springboot/...`、`*.java` などは Git Bash の書き方
- PowerShell や cmd では一部のコマンド表記が異なる
- 前提環境は JDK 17（17.x）
- Java-21 の JUnit 演習のみ Maven が必要

## 標準コースの学習順

Java全般を順番に学ぶ場合は、次の本編をすべて実施します。
1. [Java-01 ハンズオン: Javaをはじめよう](./java-01-intro.md)
2. [Java-02 ハンズオン: プログラムの書き方](./java-02-program-flow.md)
3. [Java-03 ハンズオン: 変数と型](./java-03-variables-and-types.md)
4. [Java-04 ハンズオン: 式と演算子](./java-04-expressions-and-operators.md)
5. [Java-05 ハンズオン: 代表的なクラスライブラリ](./java-05-class-libraries.md)
6. [Java-06 ハンズオン: 条件分岐と繰り返し](./java-06-conditions-and-loops.md)
7. [Java-07 ハンズオン: 配列](./java-07-arrays.md)
8. [Java-08 ハンズオン: メソッド](./java-08-methods.md)
9. [Java-09 ハンズオン: インスタンスとクラス](./java-09-instances-and-classes.md)
10. [Java-10 ハンズオン: 複数クラスを用いた開発](./java-10-multi-class-development.md)
11. [Java-11 ハンズオン: さまざまなクラス機構](./java-11-class-mechanisms.md)
12. [Java-12 ハンズオン: カプセル化](./java-12-encapsulation.md)
13. [Java-13 ハンズオン: 継承](./java-13-inheritance.md)
14. [Java-14 ハンズオン: 高度な継承](./java-14-advanced-inheritance.md)
15. [Java-15 ハンズオン: 多態性](./java-15-polymorphism.md)
16. [Java-16 ハンズオン: Javaを支える標準クラス](./java-16-standard-classes.md)
17. [Java-17 ハンズオン: 例外](./java-17-exceptions.md)
18. [Java-18 ハンズオン: コレクション](./java-18-collections.md)
19. [Java-19 ハンズオン: Stream API](./java-19-stream-api.md)
20. [Java-20 ハンズオン: Oracle Javadocの読み方](./java-20-javadoc-reading.md)

## Spring Boot向け最短コース

Spring Boot教材の読解・実装に必要なJavaだけを先に学ぶ場合は、標準コースの全章完了を前提にしません。
詳細な順序、各教材で省略できる範囲、Spring Boot側で補完する内容は、[Spring Boot向けJava最短ロードマップ](../../springboot/README.md#spring-boot向けjava最短ロードマップ)を正本とします。

### 全編を実施する教材

次の教材は原則としてハンズオンまで実施します。ミニ演習は、理解に不安がある項目だけ実施して構いません。

| 順番 | 教材 | 必要な内容 |
| ---: | --- | --- |
| 1 | [Java-01](./java-01-intro.md) | JDK 17、Maven、VS Code、Git Bashの準備 |
| 2 | [Java-03](./java-03-variables-and-types.md) | 変数、基本型、`String`、初期化 |
| 3 | [Java-04](./java-04-expressions-and-operators.md) | 比較・論理演算子による条件判定 |
| 4 | [Java-05](./java-05-class-libraries.md) | `String`、`LocalDate`、`LocalDateTime` |
| 5 | [Java-06](./java-06-conditions-and-loops.md) | `if` / `else`と基本的な繰り返し |
| 6 | [Java-08](./java-08-methods.md) | 引数、戻り値、メソッド呼び出し |
| 7 | [Java-09](./java-09-instances-and-classes.md) | クラス、インスタンス、`new` |
| 8 | [Java-09A](./java-09a-string-reference-and-value-comparison.md) | `String`を`equals`で比較する理由 |
| 9 | [Java-10](./java-10-multi-class-development.md) | クラス分割、`package`、`import` |
| 10 | [Java-11](./java-11-class-mechanisms.md) | コンストラクタ、`this`、`static` |
| 11 | [Java-12](./java-12-encapsulation.md) | `private`、getter / setter、カプセル化 |
| 12 | [Java-17](./java-17-exceptions.md) | `try` / `catch`、`throw`、例外処理 |
| 13 | [Java-17A](./java-17a-exception-types-and-throws.md) | checked / unchecked例外、`throws`、例外伝播 |
| 14 | [Java-18](./java-18-collections.md) | `List`、`Map`、ジェネリクス |
| 15 | [Java-20A](./java-20a-record-enum.md) | `enum`と`record` |
| 16 | [Java-20B](./java-20b-web-api-prep.md) | `GET` / `POST`、URL、HTTPステータス、`curl` |
| 17 | [Java-21](./java-21-junit-basics.md) | Maven、JUnit 5、`@Test`、アサーション |

Java-20BのHTMLは講師提供コードを使用し、HTML自体の実装は評価しません。

### 必要部分だけ実施する教材

| 教材 | 確認する範囲 |
| --- | --- |
| [Java-02](./java-02-program-flow.md) | Javaソースの基本構造、`main`、コンパイルエラーと実行時エラーの違い |
| [Java-04A](./java-04a-type-conversion-and-cast.md) | 文字列と数値の変換、プリミティブ型とラッパー型、明示キャストの意味 |
| [Java-07](./java-07-arrays.md) | `String[] args`、配列と`List`の違い、添字が0から始まること |
| [Java-16](./java-16-standard-classes.md) | `Object`、`equals`、`toString`、ラッパークラス |
| [Java-19](./java-19-stream-api.md) | `stream()`、`filter()`、`map()`、`toList()`、ラムダ式の読み方 |
| [Java-20](./java-20-javadoc-reading.md) | クラス概要、メソッドの引数・戻り値、APIの検索方法 |

### Spring Boot開始後へ回せる教材

Java-06A、Java-07A、Java-11A、Java-12A、Java-13 / 13A、Java-14 / 15、Java-16Aは、この最短コースの開始条件に含めません。
継承とインターフェースの最小概念はSpring Bootの各Lesson内で補い、本格的な実装演習は開始後の復習として実施します。

### 最短コースの完了条件

次をコードまたは口頭で説明できれば、省略対象の章やミニ演習が未完了でもSpring Bootへ進めます。

1. 複数クラスを`package`で分け、コンストラクタから依存オブジェクトを受け取れる
2. 引数・戻り値・`List<T>`・`Map<K, V>`を含むメソッドを読める
3. `String`を`==`ではなく`equals`で比較できる
4. `enum`で状態を表し、`record`をデータの入れ物として読める
5. `throw` / `throws` / `try-catch`とunchecked例外の伝播を説明できる
6. `GET` / `POST` / HTTPステータスの違いを説明し、`curl`でリクエストできる
7. MavenでJUnitテストを実行し、成功・失敗を判別できる

## 補講（不足項目補完 / 任意）
- [Java-06A 補講: switch / do-while / ラベル付き制御](./java-06a-advanced-control-flow.md)
- [Java-07A 補講: 参照型と多次元配列](./java-07a-reference-types-and-multidimensional-arrays.md)
- [Java-11A 補講: コンストラクタ連鎖（this / デフォルトコンストラクタ）](./java-11a-constructor-chaining.md)
- [Java-12A 補講: アクセス修飾子の使い分け](./java-12a-access-modifiers.md)
- [Java-13A 補講: 継承ルールの深掘り（super / 単一継承 / final）](./java-13a-inheritance-rules.md)
- [Java-16A 補講: 正規表現の基礎（メタ文字とエスケープ）](./java-16a-regex-basics.md)

## 読み方のルール
- `次の内容で作成` は、新しいファイルをその内容で作るという意味
- `次の内容に更新` は、前のコード全体を置き換えるという意味
- `期待出力例` は、そのStepまたはレベルで画面に表示される出力全体の例
- `確認対象の出力（抜粋）` は、既存出力を省略し、その課題で特に確認する行だけを示す
- `期待結果` は、コンパイル成功、エラー確認、挙動の違いなど、画面出力以外も含む確認結果

## 解答例
- Java-01〜Java-19 のミニ演習解答は `ミニ演習解答/` 配下に配置
- Java-20AとJava-20Bのミニ演習解答も `ミニ演習解答/` 配下に配置
- Java-20 と Java-21 は本文内に `解答例` セクションを含むため、別ファイルは作成していない
- ミニ演習解答は、各レベルについて「引き継ぐ内容」「変更・追記位置」「確認出力」を明記する
- レベル3は、差分だけでは完成状態を判断しにくい場合、レベル3完了時の全コードも掲載する

## 配布前確認

講師は[Java研修 講師事前チェック](./INSTRUCTOR_CHECKLIST.md)に従い、次のコマンドをリポジトリルートで実行します。

```powershell
powershell -ExecutionPolicy Bypass -File scripts/verify-java-handson.ps1
```

## 方針
- `docs/curriculum/java/java.md` と同じ進行スタイル
- 実務で使う内容を優先
- 各章を独立した markdown ファイルで管理
