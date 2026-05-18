# 🎁 Okuri-Bit — 気持ちを、ギフトに変えよう

## プロジェクト概要

**Okuri-Bit** は、**感情起点のギフト体験**を提供する次世代ギフトサービスです。  
「応援」「感謝」「労い」などの感情を選ぶだけでギフトを提案し、アバター演出で気持ちを届け、受け取り手がリアクションを返せる双方向ギフトプラットフォームです。

---

## 🚀 機能一覧（実装済み）

### 🏠 LP（index.html）
- ✅ フルスクリーン LP（サービス紹介・特徴・課題解決・フロー・ユーザーボイス）
- ✅ LP内CTAボタン（ギフトを贈る / もらった画面を見る / みんなの投稿 / AIに相談）
- ✅ 感情バブルクリックでgift.htmlへ直接遷移（URLパラメータ付き）
- ✅ ヘッダー固定・スクロールで背景変化

### 🎁 ギフト選択（gift.html）
- ✅ **気持ちから選ぶタブ**：8感情選択 → 単品ギフト提案 + 3択セット提案
- ✅ **全ギフトから選ぶタブ**：単品ブラウズ（カテゴリ・価格帯・検索）+ セット一覧ブラウズ
- ✅ URLパラメータ（?emotion=xxx）で感情プリセット
- ✅ 選択バナー（下部固定）・選択解除ボタン
- ✅ Giftalkへの誘導フローティングボタン

### 🤖 Giftalk AIチャット（giftalk.html）
- ✅ **5段階チャットフロー**（気持ち→相手・状況→予算→深掘り→提案）
- ✅ ステップ進捗バー表示（どのフェーズかリアルタイム確認）
- ✅ 収集した情報をコンテキストバーに表示
- ✅ クイック返信チップ（各フェーズに応じて変化）
- ✅ 単品ギフト＋3択セットを同時提案
- ✅ 「他のも見せて」「もっと安いもの」など追加深掘り対応
- ✅ チャット内ギフトカードからアバター作成へ直接遷移

### 👤 アバター作成（avatar.html）
- ✅ アバターカスタマイズ（肌・髪型・髪色・目・アクセサリー・服装）
- ✅ 表情選択（うれしい/愛してる/感謝/クール/感激/恥ずかしい/お祝い/応援）
- ✅ モーション選択（ジャンプ/手を振る/くるくる/ドキドキ/やったー/静止）
- ✅ アバターのリアルタイムプレビュー（Canvas描画）
- ✅ 過去アバター再利用

### 🎭 アバター管理（avatars.html）← NEW
- ✅ 保存済みアバターの一覧表示（Canvasリアルタイムアニメーション付き）
- ✅ 新しいアバターをストックに保存（肌/髪型/髪色/目/アクセサリー/服装/表情/モーション）
- ✅ 既存アバターの編集（全項目変更可能）
- ✅ アバターの削除（確認ダイアログ付き）
- ✅ 「使う」ボタンでsessionStorageにセット→自動でgift.htmlへ遷移
- ✅ スケルトンローディング・空のエンプティステート
- ✅ index.html / avatar.html トップナビにリンク追加

### 📝 メッセージ・決済（checkout.html）
- ✅ メッセージ入力
- ✅ 決済モック（クレジット/PayPay/LINE Pay/コンビニ）
- ✅ ギフトURL発行・LINE/メール/コピーで共有
- ✅ **セットギフト情報を `orders` テーブルに保存**（`gift_is_set`, `gift_set_items` フィールド）

### 🎁 受け取り手ページ（receive.html）
- ✅ 星空演出オープニング
- ✅ ギフトボックスタップで開封体験
- ✅ アバターモーション付き登場・メッセージ表示
- ✅ **セットギフト3択選択UI** — 3枚カードから受け取り手が1つを選択
- ✅ カード選択→決定ボタン→フェードアウト→選んだギフトリビール演出
- ✅ 選択結果を `orders` テーブルに保存（`chosen_item_name` / `chosen_item_index`）
- ✅ 単品ギフトは従来通りの1枚リビール演出
- ✅ 絵文字リアクション（6種）・テキスト返信
- ✅ リアクション後「コミュニティに投稿する」ボタン

### 📊 リアクション確認（reactions.html）
- ✅ 送ったギフト一覧・ステータス表示
- ✅ リアクション確認・統計
- ✅ 自動リフレッシュ（15秒ごと）

### 📸 コミュニティ SNS（community.html）
- ✅ ギフト受け取り体験の投稿・閲覧
- ✅ 新着順・人気順・感情タグ別フィルター
- ✅ いいね機能（ローカルセッション対応）
- ✅ 新規投稿モーダル（ニックネーム・ギフト・感情タグ・本文）
- ✅ サンプル投稿8件（初期データ）

---

## 📂 ファイル構成

```
index.html         — LP（ランディングページ）※サービス紹介専用
gift.html          — ギフト選択（感情タブ + 全ギフトタブ）
avatar.html        — アバター作成・編集
checkout.html      — メッセージ・決済・URL発行
receive.html       — 受け取り手用演出ページ
reactions.html     — リアクション確認（送り手用）
giftalk.html       — AIギフト相談チャット（Giftalk・5段階フロー）
community.html     — ギフト体験投稿・SNS閲覧
css/style.css      — 共通スタイル
README.md          — このファイル
```

---

## 🔗 ページ遷移フロー

### 送り手フロー
```
index.html（LP）
  ↓ 感情を選ぶ
  ↓ 3択セット or 単品ギフトを選ぶ
avatar.html
  ↓ アバターをカスタマイズ
checkout.html
  ↓ メッセージ → 決済 → URL発行
reactions.html（リアクション確認）
```

### 受け取り手フロー
```
receive.html?id={orderId}
  ↓ 星空演出 → タップで開封
  ↓ アバター演出 → メッセージ確認
  ↓ リアクション送信
  ↓ community.html（体験投稿へ）
```

### Giftalk フロー
```
giftalk.html
  ↓ AIとフリーチャット
  ↓ ギフトカード提案
  ↓ avatar.html（贈るフローへ）
```

---

## 🗄️ データモデル

### gift_posts（コミュニティ投稿）
| フィールド | 型 | 説明 |
|---|---|---|
| id | text | 投稿ID |
| poster_name | text | 投稿者名 |
| poster_emoji | text | アバター絵文字 |
| gift_name | text | もらったギフト名 |
| gift_emoji | text | ギフト絵文字 |
| gift_price | number | ギフト価格 |
| message | rich_text | 投稿本文 |
| sender_relation | text | 贈り手との関係 |
| emotion_tag | text | 感情タグ |
| image_emoji | text | イメージ絵文字 |
| likes | number | いいね数 |
| liked_by | text | いいねしたユーザーID（カンマ区切り） |

### orders（注文情報）
| フィールド | 型 | 説明 |
|---|---|---|
| id | text | 注文ID（`order_TIMESTAMP_RANDOM`） |
| sender_name | text | 送り手名 |
| recipient_name | text | 受け取り手名 |
| gift_id | text | ギフトID |
| gift_name | text | ギフト名 |
| gift_emoji | text | ギフト絵文字 |
| gift_price | number | ギフト価格 |
| gift_is_set | number | セットギフトフラグ（0/1） |
| gift_set_items | text | セットアイテム配列（JSON文字列） |
| chosen_item_name | text | 受け取り手が選んだアイテム名 |
| chosen_item_emoji | text | 受け取り手が選んだアイテム絵文字 |
| chosen_item_index | number | 受け取り手が選んだアイテムのインデックス |
| avatar_data | text | アバター設定JSON |
| expression | text | アバター表情 |
| motion | text | アバターモーション |
| message | text | メッセージ |
| status | text | 状態（pending/opened/chosen/reacted） |

### avatars / reactions（既存テーブル）
- アバター情報・リアクション情報の保存に使用

---

## 🎭 感情タグ一覧

| ID | ラベル | 説明 |
|---|---|---|
| cheer | 応援 | 頑張っている人への応援ギフト |
| thanks | 感謝 | お礼の気持ちを伝えるギフト |
| care | 労い | 疲れを癒やすリラックスギフト |
| hidden | 下心 | ちょっとドキドキするギフト |
| secret | 裏心 | 何かを狙っているギフト |
| duty | 義務感 | 気持ちより義理のギフト |
| self | 自己満足 | 自分が選びたいから贈るギフト |
| other | その他 | 気分で選ぶランダムギフト |

---

## 🔧 技術スタック

- **HTML5 / CSS3 / Vanilla JavaScript**（フレームワークなし）
- **Canvas API**（アバター描画・アニメーション）
- **RESTful Table API**（データ永続化）
- **Google Fonts**（Noto Sans JP / Nunito）
- **Font Awesome**（アイコン）
- **CSS Custom Properties**（デザイントークン）

---

## 📌 URIパラメータ

| ページ | パラメータ | 説明 |
|---|---|---|
| `receive.html` | `?id={orderId}` | ギフト注文IDを指定 |
| `receive.html` | `?demo=1` | デモ表示モード |

---

## 🚧 今後の開発予定

- [ ] 実際の決済連携（Stripe等）
- [ ] ユーザー認証・ログイン機能
- [ ] Giftalk AI の外部LLM API連携（本格AI化）
- [x] ~~3択セット受け取り手ページ対応（どれを選んだか通知）~~ → **実装済み**
- [ ] コミュニティ投稿への返信・コメント機能
- [ ] プッシュ通知（リアクション受信時）
- [ ] ギフト画像のアップロード・表示
- [ ] アバターの3D化・Live2D対応
- [ ] グループギフト（複数人から1人へ）
