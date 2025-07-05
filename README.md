# SQLX Dataform Highlight

Dataformプロジェクト向けSQLXファイル（`.sqlx`）のためのVS Code構文ハイライト拡張です。  
BigQuery SQLのキーワードに加え、Dataform/SQLX独自のテンプレート構文や`config`ブロックも美しく強調表示します。

---

## 特徴

- **BigQuery SQL互換のキーワードハイライト**（青系）
- **`config`ブロックやパラメータをオレンジ系で強調**
- **`{{ ... }}` テンプレート式やDataform独自関数もサポート**
- **`pre_operations`/`post_operations`ブロックも認識**
- コメント、文字列、数値、演算子なども細かく色分け

---

## 使い方

1. この拡張をインストール
2. `.sqlx`ファイルを開くだけで自動的にハイライトされます

---

## カスタマイズ例

VS Codeの`settings.json`で色を上書きできます。

```json
"editor.tokenColorCustomizations": {
  "textMateRules": [
    {
      "scope": "keyword.control.sql",
      "settings": { "foreground": "#4285F4" }
    },
    {
      "scope": [
        "keyword.other.config.sqlx",
        "variable.parameter.config.sqlx"
      ],
      "settings": { "foreground": "#FB8C00" }
    }
  ]
}
```

---

## サンプル

```sql
config {
  type: "table",
  schema: "analytics",
  tags: ["daily", "etl"]
}

-- テンプレート式
SELECT * FROM {{ ref("my_table") }}
WHERE {{ some_variable }} = true
```

---

## 対応範囲

- Dataform SQLX構文（テンプレート、config、pre/post_operations等）
- BigQuery SQLの主要キーワード・型・演算子
- コメント（`--`, `#`, `/* ... */`）
- 文字列（シングル/ダブル/バッククォート/パーセント）

---

## 貢献・フィードバック

バグ報告・機能要望・プルリクエスト歓迎です！  
Dataform/SQLXの進化やBigQuery拡張にも随時対応予定です。

---

## よくある質問

**Q: この拡張は無料ですか？**  
A: はい、完全に無料です。

**Q: どのようにバグを報告できますか？**  
A: GitHubの[リポジトリ](https://github.com/your-repo/sqlx-dataform-highlight)でイシューを作成してください。

**Q: 機能追加のリクエストはどこにすればいいですか？**  
A: 同じくGitHubのリポジトリでイシューを作成するか、プルリクエストを送ってください。

**Q: この拡張の更新頻度はどのくらいですか？**  
A: DataformやBigQueryのアップデートに合わせて、随時更新を行う予定です。

**Q: 使用している色を変更したいのですが。**  
A: VS Codeの`settings.json`で`editor.tokenColorCustomizations`を使って色をカスタマイズできます。

**Q: 他におすすめの拡張はありますか？**  
A: Dataformを使うなら、公式の[Dataform VS Code Extension](https://marketplace.visualstudio.com/items?itemName=dataform.dataform)もおすすめです。

---

## 更新履歴

- **1.0.0**: 初版リリース
- **1.0.1**: マイナーなバグ修正
- **1.1.0**: 新機能追加

---

## ライセンス

MIT License. 詳細は[LICENSE](LICENSE)ファイルを参照してください。

---

## 連絡先

何か質問があれば、気軽に[メール](mailto:your-email@example.com)してください。

---

## 参考

- [Visual Studio Code Marketplace](https://marketplace.visualstudio.com/vscode)
- [Dataform Documentation](https://docs.dataform.co/)
- [BigQuery Documentation](https://cloud.google.com/bigquery/docs)

**Enjoy!**
