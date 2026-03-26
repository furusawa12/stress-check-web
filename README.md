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
2. デフォルトでは H2 インメモリDBで起動します。追加設定は不要です。
3. MySQL を使う場合は DB を作成し、環境変数を設定してプロファイル `mysql` を有効化してください。
   ```bash
   export DB_URL='jdbc:mysql://localhost:3306/stress_check?characterEncoding=UTF-8&useSSL=false&serverTimezone=Asia/Tokyo'
   export DB_USERNAME='your_user'
   export DB_PASSWORD='your_password'
   mvn spring-boot:run -Dspring-boot.run.profiles=mysql
   ```

## 実行方法
H2（デフォルト）で起動する場合:
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
