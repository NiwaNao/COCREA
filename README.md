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

Vercelが表示するDNSレコードを、`my-artkit.com`のDNSプロバイダーで設定してください：

**CNAMEレコードの場合：**
- タイプ: `CNAME`
- 名前: `cocrea`
- 値: Vercelが指定する値（例: `cname.vercel-dns.com` または `76.76.21.21`）

**Aレコードの場合：**
- タイプ: `A`
- 名前: `cocrea`
- 値: `76.76.21.21`

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
     - "Domain not found" → DNS設定が完了していない
     - "Invalid domain" → ドメイン名の形式が正しくない
     - "Domain already in use" → 他のプロジェクトで使用中

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

