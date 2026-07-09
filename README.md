# order-management-java

Java / Web / Spring Boot 研修用の教材リポジトリです。HTML/CSS、JavaScript、Java基礎、Spring Boot、環境構築演習までを段階的に学習できるように、Markdown教材、PDF資料、ミニ演習解答、講師用チェックリストを配置しています。

## このリポジトリの位置づけ

このリポジトリは、完成済みアプリケーション本体ではなく、研修で使う教材集です。受講者は各教材に沿って、自分の作業フォルダにHTML、JavaScript、Java、Spring Bootアプリケーションを作成しながら進めます。

一部に実行可能なサンプルとして、Spring Boot Lesson1向けの Maven Sandbox が含まれています。

## 主な構成

| パス | 内容 |
| --- | --- |
| [docs/curriculum/html_css/html_css.md](docs/curriculum/html_css/html_css.md) | HTML / CSS 基礎教材 |
| [docs/curriculum/javascript/javascript.md](docs/curriculum/javascript/javascript.md) | JavaScript 基礎教材 |
| [docs/curriculum/javascript/javascript-fetch-json.md](docs/curriculum/javascript/javascript-fetch-json.md) | fetch / async / await / JSON通信の補講 |
| [docs/curriculum/java/java-handson/](docs/curriculum/java/java-handson/) | Java基礎からJUnitまでの分割ハンズオン |
| [docs/curriculum/springboot/](docs/curriculum/springboot/) | Spring Boot 学習教材 |
| [docs/curriculum/springboot/deployment/](docs/curriculum/springboot/deployment/) | VirtualBox / Docker Compose の環境演習 |
| `ミニ演習解答/` | 各章のミニ演習解答 |
| `INSTRUCTOR_CHECKLIST.md` | 講師向けの事前確認チェックリスト |

## 推奨学習順

1. [HTML / CSS 基礎](docs/curriculum/html_css/html_css.md)
2. [JavaScript 基礎](docs/curriculum/javascript/javascript.md)
3. [JavaScript fetch / JSON 補講](docs/curriculum/javascript/javascript-fetch-json.md)
4. [Java ハンズオン](docs/curriculum/java/java-handson/)
5. [Spring Boot 学習ガイド](docs/curriculum/springboot/)
6. 必要に応じて [Spring Boot 環境演習](docs/curriculum/springboot/deployment/)

短縮コースやバックエンド重視の研修では、HTML/CSS/JavaScriptを講師提供コードとして扱い、JavaとSpring Bootを中心に進める構成も想定されています。

## Java ハンズオン

Java教材は [docs/curriculum/java/java-handson/](docs/curriculum/java/java-handson/) にあります。

主な範囲:

- Javaの実行環境、作成、コンパイル、実行
- 変数、型、演算子、条件分岐、繰り返し
- 配列、メソッド、クラス、インスタンス
- カプセル化、継承、抽象クラス、インターフェース、多態性
- 標準クラス、例外、コレクション、Stream API
- Javadocの読み方、record / enum、Web API前準備、JUnit 5

入口:

- [Java ハンズオン README](docs/curriculum/java/java-handson/README.md)
- [Java研修 講師事前チェック](docs/curriculum/java/java-handson/INSTRUCTOR_CHECKLIST.md)

## Spring Boot 教材

Spring Boot教材は [docs/curriculum/springboot/](docs/curriculum/springboot/) にあります。

主な範囲:

- Lesson0: Java復習ミニ制作
- Lesson1: Maven、Spring Boot起動、Controller、Thymeleaf
- Lesson2: Entity、Repository、Service、DB連携
- Lesson3: 業務ルール、状態遷移
- Lesson4: 勤怠一覧画面、H2確認
- Lesson5: ログイン、認証、認可、管理者機能、テスト
- Lesson6: REST API、DTO、例外応答
- Lesson7: FlywayによるDBスキーマ変更管理
- 環境演習: VirtualBox / Docker Compose

入口:

- [Spring Boot 学習ガイド](docs/curriculum/springboot/README.md)
- [Spring Boot研修 講師事前チェック](docs/curriculum/springboot/INSTRUCTOR_CHECKLIST.md)

## 実行できるサンプル

Spring Boot Lesson1の Maven Sandbox は、実際にビルド・テスト・起動できます。

```bash
cd docs/curriculum/springboot/lesson01/maven-sandbox
mvn test
mvn spring-boot:run
```

起動後、ブラウザで次を確認します。

```text
http://localhost:8080/hello
http://localhost:8080/hello?name=Shinesoft
```

停止する場合は、実行中のターミナルで `Ctrl + C` を押します。

## 前提ツール

教材全体では、主に次のツールを使います。

- JDK 17
- Maven 3.9+
- Git for Windows / Git Bash
- VS Code
- Edge または Chrome
- Docker Desktop または VirtualBox（環境演習を行う場合）

各教材の冒頭に、必要なツールと確認コマンドを記載しています。

## 教材利用時の注意

- Markdown教材を正本として扱います。PDFは講師説明用または補助資料です。
- コマンド例は Git Bash 前提のものがあります。PowerShellで実行する場合は、パス表記やコマンド差分に注意してください。
- `target/` 配下は Maven のビルド生成物です。教材確認には使えますが、通常は編集対象ではありません。
- `ミニ演習解答/` は、演習後の確認や講師レビュー用です。受講中は先に本文教材を進めます。

## 講師向け

研修前には、次のチェックリストを確認します。

- [Java研修 講師事前チェック](docs/curriculum/java/java-handson/INSTRUCTOR_CHECKLIST.md)
- [Spring Boot研修 講師事前チェック](docs/curriculum/springboot/INSTRUCTOR_CHECKLIST.md)

教材の追加・修正時は、受講者が迷いやすい次の点を優先して確認してください。

- 作業フォルダとコマンド実行場所
- Git Bash / PowerShell の違い
- Java / Maven のバージョン
- コンパイルエラーと実行時エラーの切り分け
- Spring Bootの各層の役割とファイル配置
