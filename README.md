# COCREA - Coming Soon

COCREAブランドのComing Soonページです。

## カスタムドメイン設定手順

Vercelで`cocrea.my-artkit.com`を設定するには、以下の手順を実行してください：

### 1. Vercelダッシュボードでの設定

1. Vercelダッシュボード（https://vercel.com）にログイン
2. プロジェクト「コクレア2025」を選択
3. 「設定」→「ドメイン」に移動
4. 「ドメインを追加」をクリック
5. `cocrea.my-artkit.com` を入力して追加

### 2. DNS設定（重要）

現在、`cocrea.my-artkit.com`のAレコードが`76.76.21.21`に設定されていますが、Vercelでは**CNAMEレコードを推奨**しています。

**推奨：CNAMEレコードに変更**
- 既存のAレコードを削除
- 新しいCNAMEレコードを追加：
  - タイプ: `CNAME`
  - ホスト名: `cocrea`
  - 値: `cname.vercel-dns.com`
  - TTL: `3600`（またはデフォルト値）

**現在のAレコード設定（動作する場合もあります）：**
- タイプ: `A`
- ホスト名: `cocrea`
- 値: `76.76.21.21`
- TTL: `3600`

**注意：** `www.my-artkit.com`がCNAMEで`cname.vercel-dns.com`を指しているため、`cocrea`も同じCNAME設定にすることを推奨します。

### 3. よくある問題

**ドメイン追加できない場合の確認事項：**

1. **DNS設定が完了しているか確認**
   - DNS設定が反映されるまで数時間かかる場合があります
   - DNSプロパゲーションチェッカーで確認してください

2. **ドメインの所有権確認**
   - Vercelがドメインの所有権を確認できない場合、追加できません
   - `my-artkit.com`のDNS設定権限があることを確認してください

3. **Vercelのエラーメッセージを確認**
   - ドメイン追加時に表示されるエラーメッセージを確認してください
   - よくあるエラー：
     - "Domain not found" → DNS設定が完了していない、またはDNSプロパゲーション待ち
     - "Invalid domain" → ドメイン名の形式が正しくない
     - "Domain already in use" → 他のVercelプロジェクトで使用中（他のプロジェクトから削除が必要）
     - "DNS configuration error" → AレコードではなくCNAMEレコードが必要な可能性

4. **AレコードからCNAMEレコードへの変更**
   - 現在Aレコード（`76.76.21.21`）が設定されている場合、CNAMEレコード（`cname.vercel-dns.com`）に変更してみてください
   - `www.my-artkit.com`と同じ設定方法を使用

4. **Vercelのプラン確認**
   - 無料プランでもカスタムドメインは使用可能ですが、制限がある場合があります

### 4. 確認方法

DNS設定後、以下のコマンドで確認できます：

```bash
# DNS設定の確認
nslookup cocrea.my-artkit.com

# または
dig cocrea.my-artkit.com
```

DNS設定が反映されると、Vercelダッシュボードでドメインのステータスが「有効」になります。

