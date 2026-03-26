# stress-check-web

Java / Spring Boot 製のストレスチェックWebシステムのベースプロジェクトです。

## 必要環境
- Java 8+
- Maven 3.8+
- MySQL 5.7+ / 8.0+

## セットアップ
1. 依存ライブラリを取得
   ```bash
   mvn dependency:resolve
   ```
2. データベースを作成（例）
   ```sql
   CREATE DATABASE stress_check DEFAULT CHARACTER SET utf8mb4;
   ```
3. `src/main/resources/application.yml` を編集し、データベース接続情報を設定する。
   - `spring.datasource.username`
   - `spring.datasource.password`
   - 必要に応じて `spring.datasource.url`

## 実行方法
```bash
mvn spring-boot:run
```

起動後の主なエンドポイント:
- トップページ: http://localhost:8080/
- ログインページ: http://localhost:8080/login

初期認証情報（メモリ上のユーザー）:
- ユーザー名: `user`
- パスワード: `password`

## ビルドとテスト
```bash
mvn clean package
mvn test
```

## 今後の拡張例
- ストレスチェック設問／回答機能の追加
- 結果表示画面と集計機能
- 管理者向け画面・権限管理の実装
- 本番環境向けのDBマイグレーション設定（Flyway等）
